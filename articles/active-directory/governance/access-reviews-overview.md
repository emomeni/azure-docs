---
title: What are Azure AD Access Reviews? | Microsoft Docs
description: Using Azure Active Directory Access Reviews, you can control group membership and application access to meet governance, risk management, and compliance initiatives in your organization.
services: active-directory
documentationcenter: ''
author: rolyon
manager: mtillman
editor: markwahl-msft
ms.service: active-directory
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: conceptual
ms.subservice: compliance
ms.date: 01/18/2019
ms.author: rolyon
ms.reviewer: mwahl
ms.collection: M365-identity-device-management
---

# What are Azure AD Access Reviews?

Azure Active Directory (Azure AD) Access Reviews enable organizations to efficiently manage group memberships, access to enterprise applications, and role assignments. User's access can be reviewed on a regular basis to make sure only the right people have continued access.

Here's a video that provides a quick overview of access reviews:

>[!VIDEO https://www.youtube.com/embed/kDRjQQ22Wkk]

## Why are access reviews important?

Azure AD enables you to collaborate internally within your organization and with users from external organizations, such as partners. Users can join groups, invite guests, connect to cloud apps, and work remotely from their work or personal devices. The convenience of leveraging the power of self-service has led to a need for better access management capabilities.

- As new employees join, how do you ensure they have the right access to be productive?
- As people move teams or leave the company, how do you ensure their old access is removed, especially when it involves guests?
- Excessive access rights can lead to audit findings and compromises as they indicate a lack of control over access.
- You have to proactively engage with resource owners to ensure they regularly review who has access to their resources.

## When to use access reviews?

- **Too many users in privileged roles:** It's a good idea to check how many users have administrative access, how many of them are Global Administrators, and if there are any invited guests or partners that have not been removed after being assigned to do an administrative task. You can recertify the role assignment users in [Azure AD directory roles](../privileged-identity-management/pim-how-to-perform-security-review.md?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json) such as Global Administrators, or [Azure resources roles](../privileged-identity-management/pim-resource-roles-perform-access-review.md?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json) such as User Access Administrator in the [Azure AD Privileged Identity Management (PIM)](../privileged-identity-management/pim-configure.md) experience.
- **When automation is infeasible:** You can create rules for dynamic membership on security groups or Office 365 groups, but what if the HR data is not in Azure AD or if users still need access after leaving the group to train their replacement? You can then create a review on that group to ensure those who still need access should have continued access.
- **When a group is used for a new purpose:** If you have a group that is going to be synced to Azure AD, or if you plan to enable the application Salesforce for everyone in the Sales team group, it would be useful to ask the group owner to review the group membership prior to the group being used in a different risk content.
- **Business critical data access:** for certain resources, it might be required to ask people outside of IT to regularly sign off and give a justification on why they need access for auditing purposes.
- **To maintain a policy's exception list:** In an ideal world, all users would follow the access polices to secure access to your organization's resources. However, sometimes there are business cases that require you to make exceptions. As the IT admin, you can manage this task, avoid oversight of policy exceptions, and provide auditors with proof that these exceptions are reviewed regularly.
- **Ask group owners to confirm they still need guests in their groups:** Employee access might be automated with some on premises IAM, but not invited guests. If a group gives guests access to business sensitive content, then it's the group owner's responsibility to confirm the guests still have a legitimate business need for access.
- **Have reviews recur periodically:** You can set up recurring access reviews of users at set frequencies such as weekly, monthly, quarterly or annually, and the reviewers will be notified at the start of each review. Reviewers can approve or deny access with a friendly interface and with the help of smart recommendations.

## Where do you create reviews?

Depending on what you want to review, you will create your access review in Azure AD Access Reviews, Azure AD enterprise apps (in preview), or Azure AD PIM.

| Access rights of users | Reviewers can be | Review created in | Reviewer experience |
| --- | --- | --- | --- |
| Security group members</br>Office group members | Specified reviewers</br>Group owners</br>Self review | Azure AD Access Reviews</br>Azure AD groups | Access panel |
| Assigned to a connected app | Specified reviewers</br>Self review | Azure AD Access Reviews</br>Azure AD enterprise apps (in preview) | Access panel |
| Azure AD directory role | Specified reviewers</br>Self review | Azure AD PIM | Azure portal |
| Azure resource role | Specified reviewers</br>Self review | Azure AD PIM | Azure portal |

## Prerequisites

To use access reviews, you must have one of the following licenses:

- Azure AD Premium P2
- Enterprise Mobility + Security (EMS) E5 license

For more information, see [How to: Sign up for Azure Active Directory Premium](../fundamentals/active-directory-get-started-premium.md) or [Enterprise Mobility + Security E5 Trial](https://aka.ms/emse5trial).

## Get started with access reviews

To learn more about creating and performing access reviews, watch this short demo:

>[!VIDEO https://www.youtube.com/embed/6KB3TZ8Wi40]

If you are ready to deploy access reviews in your organization, follow these steps in the video to onboard, train your administrators, and create your first access review!

>[!VIDEO https://www.youtube.com/embed/X1SL2uubx9M]

## Enable access reviews

To enable access reviews, follow these steps.

1. As a Global Administrator or User Account Administrator, sign in to the [Azure portal](https://portal.azure.com) where you want to use access reviews.

1. Click **All services** and find the access reviews service.

1. Click **Access Reviews**.

    ![All services - Access Reviews](./media/access-reviews-overview/all-services-access-reviews.png)

1. In the navigation list, click **Onboard** to open the **Onboard access reviews** page.

    ![Access Reviews onboard](./media/access-reviews-overview/onboard-button.png)

1. Click **Create** to enable access reviews in the current directory.

    ![Onboard access reviews](./media/access-reviews-overview/onboard-access-reviews.png)

    The next time you start access reviews, the access review options will be enabled.

    ![Access Reviews enabled](./media/access-reviews-overview/access-reviews-enabled.png)

## Next steps

- [Create an access review of groups or applications](create-access-review.md)
- [Create an access review of users in an Azure AD administrative role](../privileged-identity-management/pim-how-to-start-security-review.md?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Review access to groups or applications](perform-access-review.md)
- [Complete an access review of groups or applications](complete-access-review.md)
