---
layout: default
title: Recruiter Intake
permalink: /recruiters/
---

<!-- Email Template:

Hi <name>,

Thank you for reaching out. I'm always excited for challenging new opportunities.

To speed up the process, please book an initial phone screen with the link below:
https://calendly.com/clickthisnick

My resume can be downloaded from:
https://www.clickthisnick.com/resources/Nicholas.Smith.Resume.pdf

I look forward to working with you,
    - Nick -->

<iframe name="hidden_iframe" id="hidden_iframe" title="Recruiter form response" hidden style="display:none;"></iframe>
<div class="jumbotron">
    <h1 id="recruiter-heading">Recruiter Intake Form</h1>
    <h3>Please fill this out to make the process as seamless and fast as possible.</h3>
    <h3>Once filled out you will get redirected to a portal which has my information.</h3>

    <form id="recruiter-form" action="https://docs.google.com/forms/d/e/1FAIpQLScPT_q2aK4LaT4x3jI3LEa40yCvjZXSwWVwPoTdLBTmET0AEA/formResponse" method="post" target="hidden_iframe" toolname="submit-recruiter-intake" tooldescription="Send a recruiter's contact details. Fill every required field. Do not submit automatically; the person confirms by pressing Submit.">
        <input type="hidden" name="fvv" value="1">
        <input type="hidden" name="pageHistory" value="0">
        <input type="hidden" name="submissionTimestamp" value="-1">
        <input type="hidden" name="fbzx" value="-3089809077760842973">
        <input type="hidden" name="partialResponse" value='[null,null,"-3089809077760842973"]'>
        <br>
    <table class="table table-hover">
        <tbody>
            <tr class="table-active">
                <td>
                    <label for="recruiter-email">What is your email address?</label>
                </td>
                <td>
                    <input id="recruiter-email" name="emailAddress" type="email" autocomplete="email" required aria-invalid="false" data-error="recruiter-email-error" toolparamdescription="Email address where Nick can reply to the recruiter."/>
                    <span id="recruiter-email-error" class="field-error">Enter an email address.</span>
                </td>
            </tr>
            <tr class="table-active">
                <td>
                    <label for="recruiter-name">What is your full name?</label>
                </td>
                <td>
                    <input id="recruiter-name" name="entry.339553748" type="text" autocomplete="name" required aria-invalid="false" data-error="recruiter-name-error" toolparamdescription="Recruiter's full name."/>
                    <span id="recruiter-name-error" class="field-error">Enter your full name.</span>
                </td>
            </tr>
            <tr class="table-active">
                <td>
                    <label for="recruiter-phone">What is the best number to reach you at?</label>
                </td>
                <td>
                    <input id="recruiter-phone" name="entry.77575126" type="tel" autocomplete="tel" required aria-invalid="false" data-error="recruiter-phone-error" toolparamdescription="Best phone number for the recruiter."/>
                    <span id="recruiter-phone-error" class="field-error">Enter a phone number.</span>
                </td>
            </tr>
            <tr class="table-active">
                <td>
                    <label for="recruiter-company">What is the name of the company you work for?</label>
                </td>
                <td>
                    <input id="recruiter-company" name="entry.1454004386" type="text" autocomplete="organization" required aria-invalid="false" data-error="recruiter-company-error" toolparamdescription="Company the recruiter works for."/>
                    <span id="recruiter-company-error" class="field-error">Enter your company name.</span>
                </td>
            </tr>
            <tr class="table-active">
                <td>
                    <label for="recruiter-hours">Generally, what are your office hours?</label>
                </td>
                <td>
                    <input id="recruiter-hours" name="entry.1831281904" type="text" required aria-invalid="false" data-error="recruiter-hours-error" toolparamdescription="Recruiter's usual office hours."/>
                    <span id="recruiter-hours-error" class="field-error">Enter your office hours.</span>
                </td>
            </tr>
            <tr class="table-active">
                <td></td>
                <td>
                    <button type="submit" id="recruiter-submit" class="btn btn-success">Submit</button>
                </td>
            </tr>
        </tbody>
    </table>
    <p id="recruiter-status" role="status" aria-live="polite"></p>
    <noscript>
        <p>This page needs JavaScript to open the next step after a successful submit. The answers are still sent. If the page stays here, email <a href="mailto:admin@clickthisnick.com">admin@clickthisnick.com</a>.</p>
    </noscript>
</form>
</div>

<script>
(function () {
  var form = document.getElementById("recruiter-form");
  var status = document.getElementById("recruiter-status");
  var frame = document.getElementById("hidden_iframe");
  var nextUrl = "{{ site.baseurl }}/hyREOVPtbabaoyLOQbqaserONMvsRMlt/";
  var started = false;
  var moved = false;

  function say(message) {
    if (status) status.textContent = message;
  }

  function go() {
    if (moved) return;
    moved = true;
    say("Information sent. Opening the next step.");
    window.location.assign(nextUrl);
  }

  if (!form) return;

  function userInvalid(el) {
    try {
      return el.matches(":user-invalid");
    } catch (error) {
      return false;
    }
  }

  function syncField(el) {
    if (!el || !el.matches || !el.matches("input, select, textarea")) return;
    if (el.type === "hidden") return;
    var invalid = userInvalid(el);
    el.setAttribute("aria-invalid", invalid ? "true" : "false");
    var errorId = el.getAttribute("data-error");
    if (!errorId) return;
    if (invalid) el.setAttribute("aria-describedby", errorId);
    else el.removeAttribute("aria-describedby");
  }

  form.addEventListener("blur", function (event) {
    syncField(event.target);
  }, true);
  form.addEventListener("change", function (event) {
    syncField(event.target);
  }, true);
  form.addEventListener("input", function (event) {
    syncField(event.target);
  }, true);

  form.addEventListener("invalid", function (event) {
    syncField(event.target);
    say("Please complete the required fields before submitting.");
  }, true);

  form.addEventListener("submit", function () {
    started = true;
    say("Sending your information.");
    window.setTimeout(go, 1500);
  });

  if (frame) {
    frame.addEventListener("load", function () {
      if (started) go();
    });
  }
})();
</script>
