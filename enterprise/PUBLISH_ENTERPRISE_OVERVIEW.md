# Publishing the DPN Enterprise Overview

GitHub Enterprise Cloud supports an Enterprise README on the Enterprise **Overview** page.

The finished DPN source is:

`enterprise/ENTERPRISE_OVERVIEW.md`

## Publish

1. Open GitHub.
2. Navigate to the DPN Enterprise account.
3. Open **Overview**.
4. Click **Create README** or **Edit**.
5. Copy the contents of `enterprise/ENTERPRISE_OVERVIEW.md`.
6. Save.

## Image rule

GitHub's Enterprise README only supports images hosted publicly. The DPN overview therefore references the public DPN organization hero from the public `.github` repository.

## Governance rule

The Enterprise Overview should remain member-safe but should still avoid:
- credentials;
- tokens;
- private network addressing;
- secret values;
- customer data;
- vulnerability reproduction details;
- internal incident evidence that belongs in a restricted system.

When the source-controlled overview changes, the Enterprise Overview should be updated to match it.
