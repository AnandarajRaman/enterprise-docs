---
layout: post
title: Manage categories | Report Server | Syncfusion
description: Describes step-by-step procedure to create, open, update, delete, and manage categories in the Bold Reports On-Premise.
platform: report-platform
documentation: ug
---

# Manage Categories

This section explains how to create, open, update, delete, and share permissions in categories on the Bold Reports On-Premise.Categories are accessible by users depends upon users's permission.

Category are displayed on the left side of report listing page.
![Category setting options](/static/assets/on-premise/images/manage-categories/category-setting-options.png)

## Open category

To open the already created category, click any category in the left panel to view the reports grouped with it.
![Open already created categories](/static/assets/on-premise/images/manage-categories/open-category.png)

## Create category

To add a new category, you should have `Create All Categories` permission.
Category can be added by the below ways,

1. While publishing the designed report to the Report Server, `New Category` option will be shown.
   ![Publish report](/static/assets/on-premise/images/manage-categories/publish-report.png)
2. While copying the reports from context menu of the report listing page.
    ![Publish report](/static/assets/on-premise/images/manage-categories/create-category.png)
3. Click on the `[+]` icon from the toolbar and click on the `Create Category` option .
    ![Create category button](/static/assets/on-premise/images/manage-categories/create-category-button.png)

Provide a name and description (optional) for the category and click **Add**.
    ![Add a new category for reports](/static/assets/on-premise/images/manage-categories/add-category.png)
    > `Read, Write, Delete` permission for that `Specific Category` is provided to the user who created the category.

## Update category

To update the category name and description of the already created category, follow these steps:

1. Click the settings option available in the category.
2. Select **Update** from the context menu.
3. Modify the name or description and click **Update**.
![Update category name and description](/static/assets/on-premise/images/manage-categories/update-category.png)

## Share category

You can set permissions to the categories to share with other users in the Report Server.

### Steps to share a category

1. Click **Actions** in the category list context menu and select **Sharing Permissions**.
![Select Sharing Permissions option](/static/assets/on-premise/images/manage-categories/category-setting-options.png)
2. Click the `Manage Access` button.
![Set permissions to share a Category](/static/assets/on-premise/images/manage-categories/share-category.png)

3. Select the permission access and the users or groups to share the Category.
    ![Add permission to Category](/static/assets/on-premise/images/manage-categories/add-permission.png)

4. After selecting the access and users or groups, click on the `Add` button.
![Add button](/static/assets/on-premise/images/manage-categories/select-category-permission.png)

>Only the user who have permission can share the category with other Report Server users.

### Remove Category permission

The user who will have specific permission can remove the shared Category permissions using the `Remove` option in the `Actions` column of the each permissions.
![Remove Permission](/static/assets/on-premise/images/manage-categories/remove-permission.png)

## Delete category

You can delete a category from the Report Server by following these steps:

1. Click **Actions** in the category list context menu.
2. Select **Delete** to delete the category.
    ![Delete created category](/static/assets/on-premise/images/manage-categories/delete-category.png)
    > Category cannot be deleted when it has reports grouped in it.

## REST API Reference

The following table illustrates the list of available APIs related to category in Bold Reports On-Premise.

<table>
    <tr>
        <th>
            Action
        </th>
        <th>
            HTTP Method
        </th>
        <th>
            Endpoint
        </th>
        <th>
            Description
        </th>
    </tr>
    <tr>
        <td>
            <a href="https://help.boldreports.com/cloud-reporting/rest-api-reference/v1.0/#operation/Items_AddCategory">AddCategory</a>
        </td>
        <td>
            POST
        </td>
        <td>
            /api/site/{tenant-name}/v1.0/categories
        </td>
        <td>
            Adds a new category to the server. Category details must be passed as input.
        </td>
    </tr>
    <tr>
        <td>
            <a href="https://help.boldreports.com/cloud-reporting/rest-api-reference/v1.0/#operation/Items_UpdateCategory">UpdateCategory</a>
        </td>
        <td>
            PUT
        </td>
        <td>
            /api/site/{tenant-name}/v1.0/categories
        </td>
        <td>
            Updates the category in the server. Updated category details must be passed as input.
        </td>
    </tr>  
        <tr>
        <td>
            <a href="https://help.boldreports.com/cloud-reporting/rest-api-reference/v1.0/#operation/Items_GetItems">GetCategory</a>
        </td>
        <td>
            GET
        </td>
        <td>
            /api/site/{tenant-name}/v1.0/items
        </td>
        <td>
            Returns the list of categories for current user. ItemType should be Category.
        </td>
    <tr>
        <td>
            <a href="https://help.boldreports.com/cloud-reporting/rest-api-reference/v1.0/#operation/Items_IsItemNameExists">IsCategoryNameExists</a>
        </td>
        <td>
            POST
        </td>
        <td>
            /api/site/{tenant-name}/v1.0/items/is-name-exists
        </td>
        <td>
            Returns an item existence whether the given category name already exists or not in server. Category name and ItemType as Category should be passed in request body.
        </td>
    </tr>
    <tr>
        <td>
            <a href="https://help.boldreports.com/cloud-reporting/rest-api-reference/v1.0/#operation/Items_GetItemDetail">GetCategoryDetail</a>
        </td>
        <td>
            GET
        </td>
        <td>
            /api/site/{tenant-name}/v1.0/items/{id}
        </td>
        <td>
            Returns the specified category details from the server. Category item ID should be passed in path parameter.
        </td>
    </tr>
        <tr>
        <td>
            <a href="https://help.boldreports.com/cloud-reporting/rest-api-reference/v1.0/#operation/Items_DeleteItem">DeleteCategory</a>
        </td>
        <td>
            DELETE
        </td>
        <td>
            /api/site/{tenant-name}/v1.0/items/{id}
        </td>
        <td>
            Deletes the specified category from the server. Category item ID should be passed in path parameter.
        </td>
    </tr>
</table>