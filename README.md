# MelpAppFeatureFile
Feature: Testing MelpApp Login Page

  Scenario: Creating an Account and Logging In
    Given I am on the MelpApp login page
    When I click on the "Sign In" button
    And I choose to create an account as an "Individual"
    And I fill in the following details:
      | Field           | Value                   |
      | Full Name       | John Doe                |
      | Email           | john.doe@example.com    |
      | Password        | mysecretpassword        |
    And I click the "Create Account" button
    And I open my Gmail inbox
    And I click on the email titled "Please verify your email address to activate MelpApp Account"
    And I click the "Verify Email" link
    And I continue by clicking the "Continue" button
    And I return to the MelpApp login page
    And I fill in the following login details:
      | Field           | Value                   |
      | Email           | john.doe@example.com    |
      | Password        | mysecretpassword        |
    And I click the "Login" button

  Scenario: Setting Up Profile and Inviting Team Members
    Given I am on the individual index page
    When I fill in the following profile details:
      | Field             | Value                   |
      | Working As        | Software Engineer       |
      | Services Offered  | Web Development         |
      | Expertise Level   | Intermediate            |
      | Location          | Seattle, WA             |
    And I click the "Get Started" button
    And I click the "Invite" button
    And I invite team members by providing their email addresses
    And I click the "Go to Dashboard" button

  Scenario: Inviting Contacts and Managing Invitations
    Given I am in the network module
    When I click on the "Invite Contact" sub-module
    And I fill in the "Enter Email" text field in the invite people popup
    And I click the "Add More" button if needed
    And I click the "Invite" button
    And I confirm the successful invitation by clicking the "OK" button
    And I go to the "My Invitations" sub-module
    And I select the "Sent" option in the middle panel filter
    And I click the "Cancel" button for any pending invitations in the network sent middle panel
