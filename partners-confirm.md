---
layout: default
title: Partner Confirmation
permalink: /partners/confirm/
---

# Partner Confirmation

This page prepares a structured confirmation email for an Evolink open-source partner listing. It does not publish your project details until the partner listing is approved.

<section id="partner-confirmation" style="max-width: 760px; margin: 24px 0;">
  <div style="border: 1px solid #d8dee4; border-radius: 8px; padding: 20px; margin-bottom: 18px;">
    <p style="margin-top: 0;"><strong>Project:</strong> <span data-field="project">your project</span></p>
    <p><strong>Support:</strong> <span data-field="support">Evolink</span></p>
    <p><strong>Tracking link:</strong> <a data-field="tracking" href="https://evolink.ai/">https://evolink.ai/</a></p>
    <p style="margin-bottom: 0;"><strong>PR context:</strong> <a data-field="pr" href="">Not provided</a></p>
  </div>

  <label for="partner-confirmation-notes"><strong>Confirmation draft</strong></label>
  <textarea id="partner-confirmation-notes" rows="18" style="box-sizing: border-box; width: 100%; margin: 8px 0 14px; font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, monospace;"></textarea>

  <p>
    <a id="partner-confirmation-mailto" href="mailto:partnerships@evolink.ai" style="display: inline-block; padding: 10px 14px; border-radius: 6px; background: #111827; color: #fff; text-decoration: none;">Send confirmation email</a>
    <button id="partner-confirmation-copy" type="button" style="padding: 10px 14px; border-radius: 6px; border: 1px solid #d8dee4; background: #fff; color: #111827;">Copy draft</button>
    <span id="partner-confirmation-copy-status" style="margin-left: 8px;"></span>
  </p>
</section>

<script>
(function () {
  const params = new URLSearchParams(window.location.search);
  const recipient = "partnerships@evolink.ai";
  const get = function (key, fallback) {
    const value = params.get(key);
    return value && value.trim() ? value.trim() : fallback;
  };
  const partner = get("partner", "");
  const project = get("project", "your project");
  const support = get("support", "Evolink");
  const tracking = get("tracking", "https://evolink.ai/");
  const pr = get("pr", "");
  const subject = "Partner confirmation: " + project;
  const body = [
    "Partner confirmation",
    "",
    "Partner slug: " + partner,
    "Project: " + project,
    "Support: " + support,
    "PR URL: " + pr,
    "Tracking link: " + tracking,
    "",
    "1. Evolink may list this project on the public Partners page: Yes / No",
    "2. Approved one-line description:",
    "",
    "3. Preferred project URL:",
    "",
    "4. Logo or avatar URL / attachment note:",
    "",
    "5. README/docs ownership: partner team / Evolink follow-up PR",
    "6. Best docs reviewer or contact:",
    "",
    "7. Blog approval: Yes / No / Later",
    "8. X announcement approval and handle: Yes / No / Later / @handle",
    "",
    "Notes:"
  ].join("\n");

  const setText = function (selector, value) {
    const node = document.querySelector(selector);
    if (node) node.textContent = value || "Not provided";
  };
  const setLink = function (selector, value) {
    const node = document.querySelector(selector);
    if (!node) return;
    if (value && /^https?:\/\//i.test(value)) {
      node.textContent = value;
      node.href = value;
    } else {
      node.textContent = "Not provided";
      node.removeAttribute("href");
    }
  };

  setText('[data-field="project"]', project);
  setText('[data-field="support"]', support);
  setLink('[data-field="tracking"]', tracking);
  setLink('[data-field="pr"]', pr);

  const textarea = document.getElementById("partner-confirmation-notes");
  const mailto = document.getElementById("partner-confirmation-mailto");
  const copy = document.getElementById("partner-confirmation-copy");
  const status = document.getElementById("partner-confirmation-copy-status");
  textarea.value = body;
  const refreshMailto = function () {
    mailto.href = "mailto:" + recipient + "?subject=" + encodeURIComponent(subject) + "&body=" + encodeURIComponent(textarea.value);
  };
  textarea.addEventListener("input", refreshMailto);
  refreshMailto();
  copy.addEventListener("click", function () {
    textarea.select();
    try {
      document.execCommand("copy");
      status.textContent = "Copied.";
    } catch (error) {
      status.textContent = "Select the draft and copy it manually.";
    }
  });
})();
</script>
