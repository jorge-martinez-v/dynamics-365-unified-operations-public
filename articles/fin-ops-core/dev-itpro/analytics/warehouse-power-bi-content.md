---
title: Warehouse performance Power BI content
description: This article describes what's included in the Warehouse performance Power BI content.
author: Mirzaab
ms.date: 12/18/2017
ms.topic: article
ms.prod: 
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 
  - 272953
ms.assetid: 4e4d4323-78cf-4ffa-8d5a-05e856c33db6
ms.search.form: WHSWarehousePerformancePowerBI
---

# Warehouse performance Power BI content

[!include [banner](../includes/banner.md)]

This article describes what's included in the **Warehouse performance** Microsoft Power BI content. It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.

## Overview

The **Warehouse performance** Power BI content was created so that warehouse and operations managers can monitor important inbound, outbound, and inventory metrics. It uses Warehouse management, product, and other transactional data from your system, and provides both an aggregate view of warehouse performance and a breakdown for vendors, product groups and products, and site and warehouses.

Warehouse managers can use the **Warehouse performance** Power BI content to measure the following three areas:

- **Inbound performance** – Measure how well a vendor is performing against customer requirements (in other words, measure delivery performance), and measure put-away performance, so that you can identify issues that involve workers or items over a period. It's important that you know whether vendors are delivering on time, early, or late, so that you can determine how vendor performance is affecting overall put-away performance. A vendor that delivers outside the dates that were agreed on can put extra pressure on the warehouse because of unexpected work, and can increase the average put-away time.
- **Shipping performance** – Measure whether your warehouse is shipping in full and on time to customers (in other words, measure outbound shipping and delivery performance), so that you can identify any issues that involve products, sites or warehouses, or dedicated customers. If you find that you're shipping late to specific areas or towns, you might have to pay more attention to transportation or account management.
- **Location inventory accuracy** – Inventory accuracy is important internal warehouse business intelligence (BI). It's very important that you determine how accurately you're counting in general. However, it's also important that you determine how accurate you are at storing items in the correct locations, and that you highlight discrepancy data, so that you can find better positions for items or initiate total counting on specific items. (Currently, the new item-based counting functionality is delivered as a hotfix.) If you're using this Power BI content to determine the correctness of on-hand inventory data per location, you can also identify theft in your shops. You can also determine whether any locations have on-hand quantities that differ from enterprise resource planning (ERP) data. Those locations might be too large, or they might be impossible to count. Alternatively, some of the physical positioning might be bad, so that it's difficult to keep a single type of item in sync with on-hand data.

## Accessing the Power BI content pack
The **Warehouse performance** Power BI content is shown on the **Warehouse performance** page (**Warehouse management** \> **Inquiries and reports** \> **Warehouse performance analysis** \> **Warehouse performance**).

## Metrics that are included in the Power BI content
The **Warehouse performance** Power BI content includes a report. This report consists of a set of metrics that are visualized as charts, tiles, and tables. The following table provides an overview of the visualizations in the **Warehouse performance** Power BI content.

| Report page                 | Charts                                   | Description |
|-----------------------------|------------------------------------------|-------------|
| Inbound Performance         | Total put aways                          | The number of put-away work lines that are processed during a given time. |
| Inbound Performance         | Put away average time                    | The average time, in hours, for all purchase order put-away lines that are processed, from registration of the items until the last put is processed. |
| Inbound Performance         | Received early                           | The number of purchase order lines that are received early. |
| Inbound Performance         | Received on time                         | The number of purchase order lines that are received on time. |
| Inbound Performance         | Received late                            | The number of purchase order lines that are received late. |
| Inbound Performance         | On time by vendor                        | A view of the percentage of purchase order lines that are received from a vendor or vendor group early, on time, and late. |
| Inbound Performance         | Dock to stock average put away (hours) | The average dock-to-stock put-away time in hours over time. |
| Inbound Performance         | Average put away by worker               | The average time, in hours, that a worker has been taking for put-away processing of purchase order lines. |
| Inbound Performance         | Average put away hour by vendor          | The average put-away time in hours by vendor or vendor group. |
| Inbound Performance         | Average put away hour by product         | The average put-away time in hours by item or item group. |
| Location inventory accuracy | Total count                              | The number of counting work lines that are processed for a given period. |
| Location inventory accuracy | Discrepancy rate                         | The total discrepancy rate as a percentage of all lines that are counted for a given period. |
| Location inventory accuracy | Count without discrepancy                | Of the total number of counting work lines that are processed, the number of lines that are processed without any discrepancy. |
| Location inventory accuracy | Items counted over time                  | The percentage of items that are counted with and without discrepancy over time. |
| Location inventory accuracy | Item quantity discrepancy greater than % | A table view of counting lines that have discrepancies that exceed a specified percentage. The table includes information about locations, items, the average discrepancy, the total counting work lines that are counted, the number of counting lines that have discrepancies for the location, the average quantity that is counted, the expected total quantity that will be counted, and the actual item quantity that is counted. |
| Location inventory accuracy | Item count by worker                     | The counting performance of workers. Performance is expressed as a percentage of counting work lines that have and don't have discrepancies. |
| Location inventory accuracy | Item count by site / warehouse           | Counting performance by the number of processed counting work lines by site or warehouse that have and don't have discrepancies. |
| Location inventory accuracy | Discrepancy rate by product              | The discrepancy rate for counting performance. The rate is expressed as a percentage of processed counting work lines by item or item group. |
| Shipping performance        | Lines shipped                            | The total number of shipment lines that are shipped over a given period. |
| Shipping performance        | Early                                    | The percentage of shipment lines that are shipped early. |
| Shipping performance        | On time                                  | The percentage of shipment lines that are shipped on time. |
| Shipping performance        | Late                                     | The percentage of shipment lines that are shipped late. |
| Shipping performance        | Shipments over time                      | The percentage of shipment lines that are shipped on time, early, or late over a given period. A trend line shows the trend for lines that are shipped on time. |
| Shipping performance        | Shipped late by city                     | A map visualization of cities and areas that are affected by late shipments. |
| Shipping performance        | Shipped by product                       | The percentage that is shipped early, on time, or late by item or item group. |
| Shipping performance        | Shipped by customer                      | The percentage that is shipped early, on time, or late by customer or customer group. |
| Shipping performance        | Shipped by site / warehouse              | The percentage that is shipped early, on time, or late by site or warehouse. |

## Understanding the data model and calculations
The following data is used to fill the report pages in the **Warehouse performance** Power BI content. This data is represented as aggregate measurements that are staged in the Entity store. The Entity store is a Microsoft SQL Server database that is optimized for analytics. For more information, see [Power BI integration with Entity store](power-bi-integration-entity-store.md).

The following key aggregate measurements are used as the basis of the content.

| Report page                 | Charts                                   | Tables                                | Calculation descriptions |
|-----------------------------|------------------------------------------|---------------------------------------|--------------------------|
| Inbound Performance         | Total put aways                          | WHSWorkLine                           | The count of work lines where the work type is **put**. |
| Inbound Performance         | Put away average time                    | WHSWorkLine                           | The sum of work lines max. time divided by the count of work lines max. time, where work lines max. time is the maximum gap between the work created date and the closed date. |
| Inbound Performance         | Received early                           | WHSWorkLine                           | The count of work lines where the work created date is earlier than the delivery date that is used. If the delivery confirmed date isn't set, use the default delivery date. |
| Inbound Performance         | Received on time                         | WHSWorkLine                           | The count of work lines where the work created date is equal to the delivery date that is used. If the delivery confirmed date isn't set, use the default delivery date. |
| Inbound Performance         | Received late                            | WHSWorkLine                           | The count of work lines where the work created date is later than the delivery date that is used. If the delivery confirmed date isn't set, use the default delivery date. |
| Inbound Performance         | On time by vendor                        | WHSWorkLine                           | Received early, Received on time, and Received late (see the descriptions earlier in this table). |
| Inbound Performance         | Dock to stock average put away (hours)   | WHSWorkLine                           | Put away average time (see the description earlier in this table). |
| Inbound Performance         | Average put away by worker               | WHSWorkLine                           | Put away average time (see the description earlier in this table). |
| Inbound Performance         | Average put away hour by vendor          | WHSWorkLine                           | Put away average time (see the description earlier in this table). |
| Inbound Performance         | Average put away hour by product         | WHSWorkLine                           | Put away average time (see the description earlier in this table). |
| Location inventory accuracy | Total count                              | WHSWorkLineCycleCount                 | Cycle counts where the absolute discrepancy quantity is equal to or more than 0 (zero). |
| Location inventory accuracy | Discrepancy rate                         | WHSWorkLineCycleCount                 | Cycle counts that have discrepancies, divided by the total count. A cycle count is considered to have discrepancies if the absolute discrepancy quantity is more than 0 (zero). |
| Location inventory accuracy | Count without discrepancy                | WHSWorkLineCycleCount                 | Cycle counts where the absolute discrepancy quantity is more than 0 (zero). |
| Location inventory accuracy | Count with discrepancy                   | WHSWorkLineCycleCount                 | Cycle counts where the absolute discrepancy quantity is equal to 0 (zero). |
| Location inventory accuracy | Items counted over time                  | WHSWorkLineCycleCount                 | Count without discrepancy and Count with discrepancy (See the descriptions earlier in this table.) |
| Location inventory accuracy | Item quantity discrepancy greater than % | WHSWorkLineCycleCount                 | The average discrepancy is the absolute discrepancy quantity divided by the expected quantity where the absolute discrepancy quantity is more than 0 (zero). The average discrepancy quantity is the average absolute discrepancy quantity where the absolute discrepancy quantity is more than 0 (zero). Count with discrepancy, Total count, Expected quantity, and Counted quantity where the whole quantity is grouped by item and location (see the descriptions earlier in this table). |
| Location inventory accuracy | Item count by worker                     | WHSWorkLineCycleCount                 | Count without discrepancy and Count with discrepancy (see the descriptions earlier in this table). |
| Location inventory accuracy | Item count by site / warehouse           | WHSWorkLineCycleCount                 | Count without discrepancy and Count with discrepancy (see the descriptions earlier in this table). |
| Location inventory accuracy | Discrepancy rate by product              | WHSWorkLineCycleCount                 | Discrepancy rate (see the description earlier in this table). |
| Shipping performance        | Lines shipped                            | SalesLine               | The count of sales lines where sales lines are shipped. |
| Shipping performance        | Early                                    | CustPackingSlipOnTimeStatus           | Sales lines where the ship date status is **1 (Early)**. Early means that the ship date of the packing slip is earlier than the confirmed ship date of the sales line. If the confirmed ship date isn't set, use the requested ship date. |
| Shipping performance        | On time                                  | CustPackingSlipOnTimeStatus           | Sales lines where the ship date status is **2 (On time)**. On time means that the ship date of the packing slip is equal to the confirmed ship date of the sales line. If the confirmed ship date isn't set, use the requested ship date. |
| Shipping performance        | Late                                     | CustPackingSlipOnTimeStatus           | Sales lines where the ship date status is **3 (Late)**. Late means that the ship date of the packing slip is later than the confirmed ship date of the sales line. If the confirmed ship date isn't set, use the requested ship date. |
| Shipping performance        | Shipments over time                      | SalesLine CustPackingSlipOnTimeStatus | Orders that are fully shipped, where the whole quantity of the sales line is shipped, plus Early, On time, and Late (see the descriptions earlier in this table). |
| Shipping performance        | Shipped late by city                     | CustPackingSlipOnTimeStatus           | Late (see the descriptions earlier in this table). |
| Shipping performance        | Shipped by product                       | CustPackingSlipOnTimeStatus           | Early, On time, and Late (see the descriptions earlier in this table). |
| Shipping performance        | Shipped by customer                      | CustPackingSlipOnTimeStatus           | Early, On time, and Late (see the descriptions earlier in this table). |
| Shipping performance        | Shipped by site / warehouse              | CustPackingSlipOnTimeStatus           | Early, On time, and Late (see the descriptions earlier in this table). |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
