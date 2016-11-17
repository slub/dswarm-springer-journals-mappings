# Springer Journals Mappings in d:swarm

A repository containing all related information to process [d:swarm](http://dswarm.org) mappings that map data that conform to the Springer Journals schema.

## Source Target Maps

You can find the source target maps that are related to these mappings in a [Google Spreads Document](https://docs.google.com/spreadsheets/d/1An31LD1CcoRbfhLOnsnChXvPQb7ydhL2K9Z_2BW1qJg/edit?usp=sharing).

## Mappings

All projects that contain mappings that map from the Springer Journals schema to a target schema.

### Mappings to UBL Intermediate Format

Following projects contain mappings from Springer Journals schema to [UBL Intermediate Format](https://github.com/ubleipzig/intermediateschema/blob/master/is-0.9.json)

(project identifier = project name)

 * 0d0087a0-6e23-821b-3a2d-b7b1a26b0177 = new_im_springer_articles_title_rel
 * 3c740d85-f2ed-015b-872e-cf6a7db6cedc = new_intermediateschema_required
 * d790a8b8-f6d4-21de-c17d-5e196166bee3 = new_im_springer_journals_author_rel
 * 6ee74302-5838-5042-7f95-138d55bc18c4 = new_im_springer_journals_identifier_rel
 * 8b15da35-0404-c07f-a9b8-8bb32f2ccc9b = new_im_springer_journals_publisher_rel
 * 452a62b3-722c-c4cb-6f3c-731d0a7fb392 = new_im_springer_journals_content_rel

### Mappings to finc Solr schema

Following projects contain mappings from Springer Journals schema to [finc Solr schema](https://github.com/finc/index/blob/master/schema.xml)

(project identifier = project name)

 * 4702d82b-9416-6b0b-4b66-3370eca6a26b = finc_springer_articles_constants
 * 8a443df7-e42f-3176-828f-d62d8989bdf4 = finc_springer_articles_identifiers_related
 * cc5cbafb-f05b-0701-b245-5d3f785b9fba = finc_springer_articles_title_related
 * 886a727e-a8c8-e5e1-fcdd-517b800cffe1 = finc_springer_articles_author_rel
 * 287804a5-e96a-0fa2-52ec-8909407d4c27 = finc_springer_articles_container_rel
 * 946e7213-dfe4-7661-7b7e-45c75bb12a57 = finc_springer_articles_article_rel
 * fd7713a8-6704-9ca6-49a8-47cdddf13040 = finc_springer_articles_publisher_rel
 * d64ecf9a-52a6-c9d8-2ca5-9b130e6da0cd = finc_springer_articles_access_rel
 * 45412a00-eb03-cd10-24e7-e0126b831e1f = finc_springer_articles_fullrecord

## TPU Configurations

[TPU](https://github.com/dswarm/task-processing-unit-for-dswarm) configurations that need to be completed with
 * paths for input and output folder and 
 * the path to the configuration that should be utilised to process the data resources (this configuration can be found at [````tpu_configs/import-springer-journals-config.json````](https://github.com/slub/dswarm-springer-journals-mappings/blob/master/tpu_configs/import-springer-journals-config.json)).

There is a TPU configuration template for running TPU tasks to process mappings from Springer Journals to
 * UBL Intermediate Format: [````tpu_configs/new_im_springer_articles-tpu.properties````](https://github.com/slub/dswarm-springer-journals-mappings/blob/master/tpu_configs/new_im_springer_articles-tpu.properties)
 * finc Solr schema: [````tpu_configs/springer_articles_tpu.properties````](https://github.com/slub/dswarm-springer-journals-mappings/blob/master/tpu_configs/springer_articles_tpu.properties)

## Sample Data

Sample data that is utilised to test the mappings in the d:swarm Back Office UI

 * [````sample_data/sample_records.xml````](https://github.com/slub/dswarm-springer-journals-mappings/blob/master/sample_data/sample_records.xml): 8 Springer Journals records processed with [xem](https://github.com/dswarm/xml-elements-masker) and the content/sub trees of the masked XML elements is escaped (i.e. including inline markup elements); utilised for testing the mappings to the UBL Intermediate Format
 * [````sample_data/sample_records_2.xml````](https://github.com/slub/dswarm-springer-journals-mappings/blob/master/sample_data/sample_records_2.xml): 5 Springer Journal records processed with [xem](https://github.com/dswarm/xml-elements-masker) and only the content/text of the masked XML elements is contained (i.e. without inline markup elements); utilised for testing the mappings to the finc Solr schema

## Projects and Data Models Content

Projects and the content of the related input data models can be inserted into a running d:swarm instance with help of the [d:swarm tools](https://github.com/dswarm/dswarm-tools)

## Note
 
 * the mapping to the institution field makes use of a lookup function in an SQL database for retrieving the holdings information (i.e. this mapping might be excluded and/or adapted, if you apply the mapping to your institution)
 * the mapping to the fullrecord field makes use of a HTTP request function to a elasticsearch instance that contains the records mapped to the UBL Intermediate Format (i.e. this database needs to be provided upfront, if you wanna fill the fullrecord field)

## Kudos

The source target maps and mappings are initial implemented by [gertho](https://github.com/gertho).
