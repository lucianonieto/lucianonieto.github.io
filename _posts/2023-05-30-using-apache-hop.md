---
layout: post
title: Using Apache Hop!
date: 2023-05-30 23:01 +0000
last_modified_at: 2023-05-30 23:11 +0000
tags: [apache-hop, etl, docker]
toc:  true
---

This use case was created from an idea to have an integration data tool for a small company, for instance.
Therefore, it is possible to use Apache Hop to integrate different kinds of systems and data.

### About Apache Hop
Apache Hop is an open-source data integration platform that provides a flexible and extensible environment for designing, orchestrating, and executing data integration workflows. It offers a wide range of connectors, transformations, and job execution capabilities, making it suitable for diverse integration scenarios.

### Objective
The purpose of this project is to showcase how Apache Hop can be utilized to enable seamless integration across different systems and data types. By leveraging its extensive set of features, users can easily connect, transform, and load data from multiple sources, enabling efficient data processing and analysis.

### Concepts
**Metadata** is by far the most important concept in all of Hop. Every item we’ll cover below is defined as metadata. 
All interactions between Hop and other components in your data architecture are done through metadata. 
### Metadata is at the core of everything in Hop.
- **Pipelines** are collections of transforms, connected by hops. All transforms in a pipeline run in parallel.
- **Workflows** are collections of actions, connected by hops. All actions in a workflow run sequentially by default.
- **Projects** are logical collections of hop code and configuration. Environments contain the environment-specific (e.g. dev, uat, prd) metadata.

### Hop
The following code is the hop definition pipeline to extract the data from Amazon dataset and ingest it in our database - doing a couple of transformations:

{% highlight xml %}
<?xml version="1.0" encoding="UTF-8"?>
<pipeline>
  <info>
    <name>amazon_products_sample_raw_ingestion</name>
    <name_sync_with_filename>Y</name_sync_with_filename>
    <description/>
    <extended_description/>
    <pipeline_version/>
    <pipeline_type>Normal</pipeline_type>
    <parameters>
    </parameters>
    <capture_transform_performance>N</capture_transform_performance>
    <transform_performance_capturing_delay>1000</transform_performance_capturing_delay>
    <transform_performance_capturing_size_limit>100</transform_performance_capturing_size_limit>
    <created_user>-</created_user>
    <created_date>2023/05/31 20:20:36.676</created_date>
    <modified_user>-</modified_user>
    <modified_date>2023/05/31 20:20:36.676</modified_date>
  </info>
  <notepads>
  </notepads>
  <order>
    <hop>
      <from>Amazon Data Ecommerce</from>
      <to>String operations</to>
      <enabled>Y</enabled>
    </hop>
    <hop>
      <from>String operations</from>
      <to>Condition isAmazonSeller</to>
      <enabled>Y</enabled>
    </hop>
    <hop>
      <from>Condition isAmazonSeller</from>
      <to>Output_YES</to>
      <enabled>Y</enabled>
    </hop>
    <hop>
      <from>Condition isAmazonSeller</from>
      <to>Output_NO</to>
      <enabled>Y</enabled>
    </hop>
  </order>
  <transform>
    <name>Amazon Data Ecommerce</name>
    <type>CSVInput</type>
    <description/>
    <distribute>Y</distribute>
    <custom_distribution/>
    <copies>1</copies>
    <partitioning>
      <method>none</method>
      <schema_name/>
    </partitioning>
    <filename>/hop/marketing_sample_for_amazon_com-ecommerce__20200101_20200131__10k_data.csv</filename>
    <filename_field/>
    <rownum_field/>
    <include_filename>N</include_filename>
    <separator>,</separator>
    <enclosure>"</enclosure>
    <header>Y</header>
    <buffer_size>50000</buffer_size>
    <lazy_conversion>Y</lazy_conversion>
    <add_filename_result>N</add_filename_result>
    <parallel>N</parallel>
    <newline_possible>N</newline_possible>
    <encoding/>
    <fields>
      <field>
        <name>Uniq Id</name>
        <type>String</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>32</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Product Name</name>
        <type>String</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>200</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Brand Name</name>
        <type>Boolean</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>-1</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Asin</name>
        <type>Boolean</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>-1</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Category</name>
        <type>String</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>147</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Upc Ean Code</name>
        <type>Boolean</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>-1</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>List Price</name>
        <type>Boolean</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>-1</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Selling Price</name>
        <type>String</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>16</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Quantity</name>
        <type>Boolean</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>-1</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Model Number</name>
        <type>String</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>24</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>About Product</name>
        <type>String</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>1577</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Product Specification</name>
        <type>String</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>552</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Technical Details</name>
        <type>String</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>1936</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Shipping Weight</name>
        <type>String</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>11</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Product Dimensions</name>
        <type>String</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>38</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Image</name>
        <type>String</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>550</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Variants</name>
        <type>String</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>1026</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Sku</name>
        <type>Boolean</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>-1</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Product Url</name>
        <type>String</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>88</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Stock</name>
        <type>Boolean</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>-1</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Product Details</name>
        <type>Boolean</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>-1</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Dimensions</name>
        <type>Boolean</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>-1</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Color</name>
        <type>Boolean</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>-1</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Ingredients</name>
        <type>Boolean</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>-1</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Direction To Use</name>
        <type>Boolean</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>-1</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Is Amazon Seller</name>
        <type>Boolean</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>-1</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Size Quantity Variant</name>
        <type>Boolean</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>-1</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
      <field>
        <name>Product Description</name>
        <type>Boolean</type>
        <format/>
        <currency>¤</currency>
        <decimal>.</decimal>
        <group>,</group>
        <length>-1</length>
        <precision>-1</precision>
        <trim_type>none</trim_type>
      </field>
    </fields>
    <attributes/>
    <GUI>
      <xloc>112</xloc>
      <yloc>112</yloc>
    </GUI>
  </transform>
  <transform>
    <name>Condition isAmazonSeller</name>
    <type>FilterRows</type>
    <description/>
    <distribute>Y</distribute>
    <custom_distribution/>
    <copies>1</copies>
    <partitioning>
      <method>none</method>
      <schema_name/>
    </partitioning>
    <compare>
      <condition>
        <conditions>
</conditions>
        <function>=</function>
        <leftvalue>Is Amazon Seller</leftvalue>
        <negated>N</negated>
        <operator>-</operator>
        <value>
          <isnull>N</isnull>
          <length>-1</length>
          <name>constant</name>
          <precision>-1</precision>
          <text>Y</text>
          <type>Boolean</type>
        </value>
      </condition>
    </compare>
    <send_false_to>Output_NO</send_false_to>
    <send_true_to>Output_YES</send_true_to>
    <attributes/>
    <GUI>
      <xloc>384</xloc>
      <yloc>112</yloc>
    </GUI>
  </transform>
  <transform>
    <name>String operations</name>
    <type>StringOperations</type>
    <description/>
    <distribute>Y</distribute>
    <custom_distribution/>
    <copies>1</copies>
    <partitioning>
      <method>none</method>
      <schema_name/>
    </partitioning>
    <fields>
      <field>
        <in_stream_name>Category</in_stream_name>
        <out_stream_name/>
        <trim_type>both</trim_type>
        <lower_upper>upper</lower_upper>
        <padding_type>none</padding_type>
        <pad_char/>
        <pad_len/>
        <init_cap>no</init_cap>
        <mask_xml>none</mask_xml>
        <digits>none</digits>
        <remove_special_characters>none</remove_special_characters>
      </field>
      <field>
        <in_stream_name>Product Name</in_stream_name>
        <out_stream_name/>
        <trim_type>both</trim_type>
        <lower_upper>upper</lower_upper>
        <padding_type>none</padding_type>
        <pad_char/>
        <pad_len/>
        <init_cap>no</init_cap>
        <mask_xml>none</mask_xml>
        <digits>none</digits>
        <remove_special_characters>none</remove_special_characters>
      </field>
    </fields>
    <attributes/>
    <GUI>
      <xloc>256</xloc>
      <yloc>112</yloc>
    </GUI>
  </transform>
  <transform>
    <name>Output_YES</name>
    <type>TableOutput</type>
    <description/>
    <distribute>Y</distribute>
    <custom_distribution/>
    <copies>1</copies>
    <partitioning>
      <method>none</method>
      <schema_name/>
    </partitioning>
    <commit>1000</commit>
    <connection>postgresql</connection>
    <fields>
</fields>
    <ignore_errors>N</ignore_errors>
    <only_when_have_rows>N</only_when_have_rows>
    <partitioning_daily>N</partitioning_daily>
    <partitioning_enabled>N</partitioning_enabled>
    <partitioning_field/>
    <partitioning_monthly>Y</partitioning_monthly>
    <return_field/>
    <return_keys>N</return_keys>
    <schema>public</schema>
    <specify_fields>N</specify_fields>
    <table>curated_amazon_products_first</table>
    <tablename_field/>
    <tablename_in_field>N</tablename_in_field>
    <tablename_in_table>Y</tablename_in_table>
    <truncate>Y</truncate>
    <use_batch>Y</use_batch>
    <attributes/>
    <GUI>
      <xloc>544</xloc>
      <yloc>64</yloc>
    </GUI>
  </transform>
  <transform>
    <name>Output_NO</name>
    <type>TableOutput</type>
    <description/>
    <distribute>Y</distribute>
    <custom_distribution/>
    <copies>1</copies>
    <partitioning>
      <method>none</method>
      <schema_name/>
    </partitioning>
    <commit>1000</commit>
    <connection>postgresql</connection>
    <fields>
</fields>
    <ignore_errors>N</ignore_errors>
    <only_when_have_rows>N</only_when_have_rows>
    <partitioning_daily>N</partitioning_daily>
    <partitioning_enabled>N</partitioning_enabled>
    <partitioning_field/>
    <partitioning_monthly>Y</partitioning_monthly>
    <return_field/>
    <return_keys>N</return_keys>
    <schema>"public"</schema>
    <specify_fields>N</specify_fields>
    <table>curated_amazon_products_third</table>
    <tablename_field/>
    <tablename_in_field>N</tablename_in_field>
    <tablename_in_table>Y</tablename_in_table>
    <truncate>Y</truncate>
    <use_batch>Y</use_batch>
    <attributes/>
    <GUI>
      <xloc>544</xloc>
      <yloc>160</yloc>
    </GUI>
  </transform>
  <transform_error_handling>
  </transform_error_handling>
  <attributes/>
</pipeline>
{% endhighlight %}

### Pipeline
![data](/imgs/hop2.jpeg)

### Installation
To get started with this project, follow the steps below:

1. Clone this repository to your local machine and install the libraries:
{% highlight console %}
   git clone https://github.com/lucnietoX/di-apachehop-postgresql.git
{% endhighlight %}
   
2. Perform access permissions into all ports
3. Execute docker composer & pipelines

### Docker file
![data](/imgs/hop1.png)

### Source
Kaggle dataset - Amazon Product: **(https://www.kaggle.com/datasets/promptcloud/amazon-product-dataset-2020?resource=download)**

### More

- GitHub Repo **[here](https://github.com/lucnietoX/di-apachehop-postgresql.git)**.