# EZ-6016 — Excess Underlying Insurance Currency Entry

## Purpose

Verify that Excess underlying-insurance limits accept currency together with amounts, allow a supported currency different from the policy currency, and retain the entered values through issuance and generated documents.

Run both flows below. Use a valid submission for the existing-submission flow and a valid contract ID for the Received Liability flow. Complete fields marked mandatory by the application. For coverage checks, use values accepted by the application's configured currency and limit validation rules; include at least one currency that differs from the policy currency.

## Flow A — EzDocs Liability (existing submission)

1. Sign in to the EzDocs application with an account authorized to create or update liability submissions.
2. Select **EzDocs Liability** as the line of business.
3. Open **Search Submission**.
4. Enter a valid submission number and select **Get Submission**.
5. On the **Submission Details** screen, review the details returned from UWD. Confirm the submission is the intended account, then select **Next**.
6. On the **Information** screen, select **Excess** as the product.
7. Complete all mandatory Information fields and continue to **Coverages**.
8. In **Underlying Insurance**, verify that each of the following is a text input:
   - Occurrence Limit
   - Other Aggregate Limit
   - Products-Completed Operations Aggregate Limit
9. Enter a valid currency and limit amount in each field. Include at least one valid currency different from the policy currency. Confirm the application retains each complete entry and does not replace its currency with the policy currency.
10. In **Other Limit**, add or use an applicable row and verify its **Limit of Liability** is a text input.
11. Enter a valid currency and limit amount in the Other Limit row. If more than one row is available, verify values can be entered independently without changing another row.
12. Continue through the workflow and create the quote, binder, and policy, completing any required steps presented by the application.
13. Generate the applicable documents.
14. Review the Coverages details and generated documents. Confirm that all four limit types show the correct currency and amount and remain associated with the correct field or Other Limit row.

## Flow B — Received Liability (new submission)

1. Sign in to the EzDocs application with an account authorized to create liability submissions.
2. Select **Received Liability** as the line of business.
3. Open **Search Submission**.
4. Enter a valid contract ID and select **Get Submission**.
5. In the **Create Submission** section, complete all mandatory fields and select **Next**.
6. On the **Information** screen, select **Excess** as the product.
7. Complete all mandatory Information fields and continue to **Coverages**.
8. In **Underlying Insurance**, verify that Occurrence Limit, Other Aggregate Limit, and Products-Completed Operations Aggregate Limit are text inputs.
9. Enter a valid currency and limit amount in each field. Include at least one valid currency different from the policy currency. Confirm that the complete entries are retained.
10. In **Other Limit**, add or use an applicable row and verify its **Limit of Liability** is a text input that accepts a valid currency and limit amount.
11. Continue through the workflow and create the quote, binder, and policy if those actions are available for the submission, completing any required steps presented by the application.
12. Generate the applicable documents.
13. Review the Coverages details and generated documents. Confirm that each currency and amount is correct, is not replaced by the policy currency, and appears against the correct field or Other Limit row.

## Expected Results

- The three Underlying Insurance aggregate/occurrence fields and each Other Limit **Limit of Liability** field accept currency together with the limit amount.
- Values in a supported non-policy currency are retained without silent conversion to the policy currency.
- Each value remains associated with its own field or Other Limit row throughout the workflow.
- Quote, binder, policy, and generated documents (where available in the flow) show the corresponding entered currency and amount.
- Invalid entries, if tested, are handled according to the application's configured validation rules and are not silently truncated or altered.