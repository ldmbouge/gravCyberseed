---
title: Student-Registration
visible: false
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
        team_name:
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
        faculty_advisor_email:
            label: 'Faculty Advisor Email'
            placeholder: 'Enter your faculty advisor''s email address'
            type: email
            validate:
                required: true
        team-member-1:
            label: 'Team Member 1'
            placeholder: 'Enter name of team member 1'
            autocomplete: 'on'
            type: text
            validate:
                required: true
        team_member_1_email:
            label: 'Team Member 1 Email'
            placeholder: 'Enter team member 1''s email address'
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
        team_member_2_email:
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
        code-of-conduct:
            label: 'I have read and will comply with the UConn student code of conduct guidelines'
            type: checkbox
            validate:
                required: true
    buttons:
        submit:
            type: submit
            value: Submit
        reset:
            type: reset
            value: Reset
    process:
        save:
            fileprefix: registration-
            dateformat: Ymd-His-u
            extension: txt
            body: '{% include ''forms/data.txt.twig'' %}'
        email:
            subject: '[CyberSEED Registration] {{ form.value.college|e }} {{ form.value.team_name|e }}'
            to: '{{ form.value.faculty_advisor_email }}'
            cc:
                - '{{ config.plugins.email.to }}'
                - '{{ form.value.team_member_1_email }}'
                - '{{ form.value.team_member_2_email }}'
            body: 'Thank you for registering your team! {% include ''forms/data.html.twig'' %}'
        message: 'Thank you for registering your team!'
        display: thankyou
---

