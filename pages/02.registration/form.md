---
title: Registration
form:
    name: contact
    fields:
        college:
            label: College
            placeholder: 'Enter your college/university'
            autocomplete: 'on'
            type: text
            validate:
                required: true
        team-name:
            label: 'Team Name'
            placeholder: 'Enter your team name'
            autocomplete: 'on'
            type: text
            validate:
                required: true
        faculty-advisor:
            label: 'Faculty Advisor'
            placeholder: 'Enter name of faculty advisor'
            autocomplete: 'on'
            type: text
            validate:
                required: true
        faculty-advisor-email:
            label: 'Faculty Advisor Email'
            placeholder: 'Enter your faculty advisor''s email address'
            type: email
            validate:
                required: true
        team-captain:
            label: 'Team Captain'
            placeholder: 'Enter name of team captain'
            autocomplete: 'on'
            type: text
            validate:
                required: true
        team-captain-email:
            label: 'Team Captain Email'
            placeholder: 'Enter your team captain''s email address'
            type: email
            validate:
                required: true
        team-member-2:
            label: 'Team Member 2'
            placeholder: 'Enter name of team member 2'
            autocomplete: 'on'
            type: text
            validate:
                required: true
        team-member-2-email:
            label: 'Team Member 2 Email'
            placeholder: 'Enter team member 2''s email address'
            type: email
            validate:
                required: true
        team-member-3:
            label: 'Team Member 3'
            placeholder: 'Enter name of team member 3'
            autocomplete: 'on'
            type: text
            validate:
                required: false
        team-member-3-email:
            label: 'Team Member 3 Email'
            placeholder: 'Enter team member 3''s email address'
            type: email
            validate:
                required: false
        team-member-4:
            label: 'Team Member 4'
            placeholder: 'Enter name of team member 4'
            autocomplete: 'on'
            type: text
            validate:
                required: false
        team-member-4-email:
            label: 'Team Member 4 Email'
            placeholder: 'Enter team member 4''s email address'
            type: email
            validate:
                required: false
    buttons:
        submit:
            type: submit
            value: Submit
        reset:
            type: reset
            value: Reset
    process:
        save:
            fileprefix: contact-
            dateformat: Ymd-His-u
            extension: txt
            body: '{% include ''forms/data.txt.twig'' %}'
        email:
            subject: '[CyberSEED Registration] {{ form.value.team-name|e }}'
            body: '{% include ''forms/data.html.twig'' %}'
        message: 'Thank you for registering your team!'
        display: thankyou
---

# Registration form

Fill out the form below making sure to fill out all required fields.  You will receive a confirmation email.  If you have any questions, please contact Jeannette Burke (jeannette.burke@uconn.edu)