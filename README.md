# NGS_Galaxy_workflows

Here you can find the workflows for the Galaxy tutorials followed.

### A short introduction to Galaxy
![image](https://github.com/Eefje-Kuijpers/NGS_Galaxy_workflows/assets/13732259/f97921d0-617d-4c3b-a785-49d5827d67a3)
[Uploading Galaxy-Workf{
    "a_galaxy_workflow": "true",
    "annotation": "",
    "format-version": "0.1",
    "name": "Workflow constructed from history 'NGS analysis'",
    "steps": {
        "0": {
            "annotation": "",
            "content_id": null,
            "errors": null,
            "id": 0,
            "input_connections": {},
            "inputs": [
                {
                    "description": "",
                    "name": "SraRunInfo (1).csv"
                }
            ],
            "label": "SraRunInfo (1).csv",
            "name": "Input dataset",
            "outputs": [],
            "position": {
                "left": 10,
                "top": 10
            },
            "tool_id": null,
            "tool_state": "{\"optional\": false, \"tag\": null}",
            "tool_version": null,
            "type": "data_input",
            "uuid": "2337c02d-2db9-48ca-bc97-f31ae878536d",
            "when": null,
            "workflow_outputs": []
        },
        "1": {
            "annotation": "",
            "content_id": null,
            "errors": null,
            "id": 1,
            "input_connections": {},
            "inputs": [
                {
                    "description": "",
                    "name": "Genome"
                }
            ],
            "label": "Genome",
            "name": "Input dataset",
            "outputs": [],
            "position": {
                "left": 10,
                "top": 130
            },
            "tool_id": null,
            "tool_state": "{\"optional\": false, \"tag\": null}",
            "tool_version": null,
            "type": "data_input",
            "uuid": "97dbb926-ca29-4034-8624-4d4e01a325bd",
            "when": null,
            "workflow_outputs": []
        },
        "2": {
            "annotation": "",
            "content_id": "Grep1",
            "errors": null,
            "id": 2,
            "input_connections": {
                "input": {
                    "id": 0,
                    "output_name": "output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Select",
            "outputs": [
                {
                    "name": "out_file1",
                    "type": "input"
                }
            ],
            "position": {
                "left": 230,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "Grep1",
            "tool_state": "{\"__input_ext\": \"input\", \"chromInfo\": \"/opt/galaxy/tool-data/shared/ucsc/chrom/?.len\", \"input\": null, \"invert\": \"\", \"keep_header\": false, \"pattern\": \"SRR12733957|SRR11954102\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.0.4",
            "type": "tool",
            "uuid": "d0de4def-b5ac-4120-a3d8-170f4f0aa9a3",
            "when": null,
            "workflow_outputs": []
        },
        "3": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/bgruening/text_processing/tp_cut_tool/1.1.0",
            "errors": null,
            "id": 3,
            "input_connections": {
                "input": {
                    "id": 2,
                    "output_name": "out_file1"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Advanced Cut",
            "outputs": [
                {
                    "name": "output",
                    "type": "tabular"
                }
            ],
            "position": {
                "left": 450,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/bgruening/text_processing/tp_cut_tool/1.1.0",
            "tool_shed_repository": {
                "changeset_revision": "ddf54b12c295",
                "name": "text_processing",
                "owner": "bgruening",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"csv\", \"chromInfo\": \"/opt/galaxy/tool-data/shared/ucsc/chrom/?.len\", \"complement\": \"\", \"cut_type_options\": {\"cut_element\": \"-f\", \"__current_case__\": 0, \"list\": [\"1\"]}, \"delimiter\": \",\", \"input\": null, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.1.0",
            "type": "tool",
            "uuid": "e464f22e-5f55-4333-8ed5-a53b2d79215a",
            "when": null,
            "workflow_outputs": []
        },
        "4": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/sra_tools/fasterq_dump/3.0.8+galaxy1",
            "errors": null,
            "id": 4,
            "input_connections": {
                "input|file_list": {
                    "id": 3,
                    "output_name": "output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Faster Download and Extract Reads in FASTQ",
            "outputs": [
                {
                    "name": "list_paired",
                    "type": "input"
                },
                {
                    "name": "output_collection",
                    "type": "input"
                },
                {
                    "name": "output_collection_other",
                    "type": "input"
                },
                {
                    "name": "log",
                    "type": "txt"
                }
            ],
            "position": {
                "left": 670,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/sra_tools/fasterq_dump/3.0.8+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e407b9da183a",
                "name": "sra_tools",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"input\", \"adv\": {\"seq_defline\": \"@$sn/$ri\", \"minlen\": null, \"split\": \"--split-3\", \"skip_technical\": true}, \"chromInfo\": \"/opt/galaxy/tool-data/shared/ucsc/chrom/?.len\", \"input\": {\"input_select\": \"file_list\", \"__current_case__\": 2, \"file_list\": null}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "3.0.8+galaxy1",
            "type": "tool",
            "uuid": "4110f50f-e06b-4c69-863e-89e2b3f8808b",
            "when": null,
            "workflow_outputs": []
        },
        "5": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/fastp/fastp/0.23.2+galaxy0",
            "errors": null,
            "id": 5,
            "input_connections": {
                "single_paired|paired_input": {
                    "id": 4,
                    "output_name": "list_paired"
                }
            },
            "inputs": [],
            "label": null,
            "name": "fastp",
            "outputs": [
                {
                    "name": "output_paired_coll",
                    "type": "input"
                },
                {
                    "name": "report_html",
                    "type": "html"
                },
                {
                    "name": "report_json",
                    "type": "json"
                }
            ],
            "position": {
                "left": 890,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/fastp/fastp/0.23.2+galaxy0",
            "tool_shed_repository": {
                "changeset_revision": "65b93b623c77",
                "name": "fastp",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger.gz\", \"chromInfo\": \"/opt/galaxy/tool-data/shared/ucsc/chrom/?.len\", \"filter_options\": {\"quality_filtering_options\": {\"disable_quality_filtering\": false, \"qualified_quality_phred\": null, \"unqualified_percent_limit\": null, \"n_base_limit\": null}, \"length_filtering_options\": {\"disable_length_filtering\": false, \"length_required\": null, \"length_limit\": null}, \"low_complexity_filter\": {\"enable_low_complexity_filter\": false, \"complexity_threshold\": null}}, \"output_options\": {\"report_html\": true, \"report_json\": true}, \"overrepresented_sequence_analysis\": {\"overrepresentation_analysis\": false, \"overrepresentation_sampling\": null}, \"read_mod_options\": {\"polyg_tail_trimming\": {\"trimming_select\": \"\", \"__current_case__\": 1, \"poly_g_min_len\": null}, \"polyx_tail_trimming\": {\"polyx_trimming_select\": \"\", \"__current_case__\": 1}, \"umi_processing\": {\"umi\": false, \"umi_loc\": null, \"umi_len\": null, \"umi_prefix\": null}, \"cutting_by_quality_options\": {\"cut_by_quality5\": false, \"cut_by_quality3\": false, \"cut_window_size\": null, \"cut_mean_quality\": null}, \"base_correction_options\": {\"correction\": false}}, \"single_paired\": {\"single_paired_selector\": \"paired_collection\", \"__current_case__\": 2, \"paired_input\": null, \"adapter_trimming_options\": {\"disable_adapter_trimming\": false, \"adapter_sequence1\": null, \"adapter_sequence2\": null}, \"global_trimming_options\": {\"trim_front1\": null, \"trim_tail1\": null, \"trim_front2\": null, \"trim_tail2\": null}}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.23.2+galaxy0",
            "type": "tool",
            "uuid": "13ce4d64-b27f-404f-a632-dee8a2f152ee",
            "when": null,
            "workflow_outputs": []
        },
        "6": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/bwa/bwa_mem/0.7.17.2",
            "errors": null,
            "id": 6,
            "input_connections": {
                "fastq_input|fastq_input1": {
                    "id": 5,
                    "output_name": "output_paired_coll"
                },
                "reference_source|ref_file": {
                    "id": 1,
                    "output_name": "output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Map with BWA-MEM",
            "outputs": [
                {
                    "name": "bam_output",
                    "type": "bam"
                }
            ],
            "position": {
                "left": 1110,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/bwa/bwa_mem/0.7.17.2",
            "tool_shed_repository": {
                "changeset_revision": "e188dc7a68e6",
                "name": "bwa",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"auto\", \"analysis_type\": {\"analysis_type_selector\": \"illumina\", \"__current_case__\": 0}, \"chromInfo\": \"/opt/galaxy/tool-data/shared/ucsc/chrom/?.len\", \"fastq_input\": {\"fastq_input_selector\": \"paired_collection\", \"__current_case__\": 2, \"fastq_input1\": null, \"iset_stats\": null}, \"output_sort\": \"coordinate\", \"reference_source\": {\"reference_source_selector\": \"history\", \"__current_case__\": 1, \"ref_file\": null, \"index_a\": \"auto\"}, \"rg\": {\"rg_selector\": \"do_not_set\", \"__current_case__\": 3}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.7.17.2",
            "type": "tool",
            "uuid": "da708994-2182-4969-9109-9f80e4dc5e5f",
            "when": null,
            "workflow_outputs": []
        },
        "7": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/picard/picard_MarkDuplicates/2.18.2.4",
            "errors": null,
            "id": 7,
            "input_connections": {
                "inputFile": {
                    "id": 6,
                    "output_name": "bam_output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "MarkDuplicates",
            "outputs": [
                {
                    "name": "metrics_file",
                    "type": "txt"
                },
                {
                    "name": "outFile",
                    "type": "bam"
                }
            ],
            "position": {
                "left": 1330,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/picard/picard_MarkDuplicates/2.18.2.4",
            "tool_shed_repository": {
                "changeset_revision": "f9242e01365a",
                "name": "picard",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"bam\", \"assume_sorted\": true, \"barcode_tag\": null, \"chromInfo\": \"/opt/galaxy/tool-data/shared/ucsc/chrom/?.len\", \"comments\": [], \"duplicate_scoring_strategy\": \"SUM_OF_BASE_QUALITIES\", \"inputFile\": null, \"inputFile|__identifier__\": \"SRR11954102\", \"optical_duplicate_pixel_distance\": \"100\", \"read_name_regex\": \"\", \"remove_duplicates\": true, \"validation_stringency\": \"LENIENT\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.18.2.4",
            "type": "tool",
            "uuid": "207bd7aa-2ed3-4bba-a30b-897cfb01994f",
            "when": null,
            "workflow_outputs": []
        },
        "8": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/lofreq_viterbi/lofreq_viterbi/2.1.5+galaxy0",
            "errors": null,
            "id": 8,
            "input_connections": {
                "reads": {
                    "id": 7,
                    "output_name": "outFile"
                },
                "reference_source|ref": {
                    "id": 1,
                    "output_name": "output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Realign reads",
            "outputs": [
                {
                    "name": "realigned",
                    "type": "bam"
                }
            ],
            "position": {
                "left": 1550,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/lofreq_viterbi/lofreq_viterbi/2.1.5+galaxy0",
            "tool_shed_repository": {
                "changeset_revision": "aa35ee7f3ab2",
                "name": "lofreq_viterbi",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"input\", \"adv_options\": {\"keepflags\": false, \"bq2_handling\": {\"replace_bq2\": \"keep\", \"__current_case__\": 0, \"defqual\": \"2\"}}, \"chromInfo\": \"/opt/galaxy/tool-data/shared/ucsc/chrom/?.len\", \"reads\": null, \"reads|__identifier__\": \"SRR11954102\", \"reference_source\": {\"ref_selector\": \"history\", \"__current_case__\": 1, \"ref\": null}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.1.5+galaxy0",
            "type": "tool",
            "uuid": "c5e6497d-9cc1-42c7-a6ed-4f9d758236e0",
            "when": null,
            "workflow_outputs": []
        },
        "9": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/multiqc/multiqc/1.11+galaxy1",
            "errors": null,
            "id": 9,
            "input_connections": {
                "results_0|software_cond|input": {
                    "id": 5,
                    "output_name": "report_json"
                },
                "results_1|software_cond|output_0|input": {
                    "id": 7,
                    "output_name": "metrics_file"
                }
            },
            "inputs": [],
            "label": null,
            "name": "MultiQC",
            "outputs": [
                {
                    "name": "stats",
                    "type": "input"
                },
                {
                    "name": "html_report",
                    "type": "html"
                }
            ],
            "position": {
                "left": 1550,
                "top": 130
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/multiqc/multiqc/1.11+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "abfd8a6544d7",
                "name": "multiqc",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"input\", \"chromInfo\": \"/opt/galaxy/tool-data/shared/ucsc/chrom/?.len\", \"comment\": \"\", \"export\": false, \"flat\": false, \"results\": [{\"__index__\": 0, \"software_cond\": {\"software\": \"fastp\", \"__current_case__\": 7, \"input\": null}}, {\"__index__\": 1, \"software_cond\": {\"software\": \"picard\", \"__current_case__\": 17, \"output\": [{\"__index__\": 0, \"type\": \"markdups\", \"input\": null}]}}], \"saveLog\": false, \"title\": \"\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.11+galaxy1",
            "type": "tool",
            "uuid": "a372e055-c83c-41f7-9cdf-3b953bbe6c1b",
            "when": null,
            "workflow_outputs": []
        },
        "10": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/lofreq_indelqual/lofreq_indelqual/2.1.5+galaxy1",
            "errors": null,
            "id": 10,
            "input_connections": {
                "reads": {
                    "id": 8,
                    "output_name": "realigned"
                },
                "strategy|reference_source|ref": {
                    "id": 1,
                    "output_name": "output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Insert indel qualities",
            "outputs": [
                {
                    "name": "output",
                    "type": "bam"
                }
            ],
            "position": {
                "left": 1770,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/lofreq_indelqual/lofreq_indelqual/2.1.5+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "971e07ca4456",
                "name": "lofreq_indelqual",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"input\", \"chromInfo\": \"/opt/galaxy/tool-data/shared/ucsc/chrom/?.len\", \"reads\": null, \"reads|__identifier__\": \"SRR11954102\", \"strategy\": {\"selector\": \"dindel\", \"__current_case__\": 1, \"reference_source\": {\"ref_selector\": \"history\", \"__current_case__\": 1, \"ref\": null}}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.1.5+galaxy1",
            "type": "tool",
            "uuid": "1da5e91f-de09-49bd-b2bc-bfab0830906b",
            "when": null,
            "workflow_outputs": []
        },
        "11": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/lofreq_call/lofreq_call/2.1.5+galaxy2",
            "errors": null,
            "id": 11,
            "input_connections": {
                "reads": {
                    "id": 10,
                    "output_name": "output"
                },
                "reference_source|ref": {
                    "id": 1,
                    "output_name": "output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Call variants",
            "outputs": [
                {
                    "name": "variants",
                    "type": "vcf"
                }
            ],
            "position": {
                "left": 1990,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/lofreq_call/lofreq_call/2.1.5+galaxy2",
            "tool_shed_repository": {
                "changeset_revision": "4805fe3d8fda",
                "name": "lofreq_call",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"input\", \"call_control\": {\"set_call_options\": \"yes\", \"__current_case__\": 1, \"coverage\": {\"min_cov\": \"50\", \"max_depth\": \"1000000\"}, \"pe\": {\"use_orphan\": false}, \"bc_quals\": {\"min_bq\": \"30\", \"min_alt_bq\": \"30\", \"alt_bq\": {\"modify\": \"\", \"__current_case__\": 0}}, \"align_quals\": {\"alnqual\": {\"use_alnqual\": \"\", \"__current_case__\": 0, \"alnqual_choice\": {\"alnquals_to_use\": \"\", \"__current_case__\": 1, \"extended_baq\": true}}}, \"map_quals\": {\"min_mq\": \"20\", \"use_mq\": {\"no_mq\": \"\", \"__current_case__\": 0, \"max_mq\": \"255\"}}, \"source_qual\": {\"use_src_qual\": {\"src_qual\": \"\", \"__current_case__\": 0}}, \"joint_qual\": {\"min_jq\": \"0\", \"min_alt_jq\": \"0\", \"def_alt_jq\": \"0\"}}, \"chromInfo\": \"/opt/galaxy/tool-data/shared/ucsc/chrom/?.len\", \"filter_control\": {\"filter_type\": \"set_lofreq_standard\", \"__current_case__\": 2, \"sig\": \"0.01\", \"bonf\": \"dynamic\", \"others\": \"\"}, \"reads\": null, \"reads|__identifier__\": \"SRR11954102\", \"reference_source\": {\"ref_selector\": \"history\", \"__current_case__\": 1, \"ref\": null}, \"regions\": {\"restrict_to_region\": \"genome\", \"__current_case__\": 0}, \"variant_types\": \"--call-indels\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.1.5+galaxy2",
            "type": "tool",
            "uuid": "144d8be5-cb5c-42c2-b402-f68e8cd1feda",
            "when": null,
            "workflow_outputs": []
        },
        "12": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/snpeff_sars_cov_2/snpeff_sars_cov_2/4.5covid19",
            "errors": null,
            "id": 12,
            "input_connections": {
                "input": {
                    "id": 11,
                    "output_name": "variants"
                }
            },
            "inputs": [],
            "label": null,
            "name": "SnpEff eff:",
            "outputs": [
                {
                    "name": "snpeff_output",
                    "type": "vcf"
                },
                {
                    "name": "statsFile",
                    "type": "html"
                },
                {
                    "name": "csvFile",
                    "type": "csv"
                }
            ],
            "position": {
                "left": 2210,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/snpeff_sars_cov_2/snpeff_sars_cov_2/4.5covid19",
            "tool_shed_repository": {
                "changeset_revision": "2a3a00c1fa0a",
                "name": "snpeff_sars_cov_2",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"vcf\", \"annotations\": null, \"chr\": null, \"chromInfo\": \"/opt/galaxy/tool-data/shared/ucsc/chrom/?.len\", \"csvStats\": true, \"filter\": {\"specificEffects\": \"no\", \"__current_case__\": 0}, \"filterOut\": null, \"generate_stats\": true, \"genome_version\": \"NC_045512.2\", \"input\": null, \"inputFormat\": \"vcf\", \"input|__identifier__\": \"SRR11954102\", \"intervals\": null, \"noLog\": true, \"offset\": \"default\", \"outputConditional\": {\"outputFormat\": \"vcf\", \"__current_case__\": 0}, \"transcripts\": null, \"udLength\": \"0\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "4.5covid19",
            "type": "tool",
            "uuid": "811d82e9-812b-48f4-8b4b-3937cdaa05b6",
            "when": null,
            "workflow_outputs": []
        },
        "13": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/snpsift/snpSift_extractFields/4.3+t.galaxy0",
            "errors": null,
            "id": 13,
            "input_connections": {
                "input": {
                    "id": 12,
                    "output_name": "snpeff_output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "SnpSift Extract Fields",
            "outputs": [
                {
                    "name": "output",
                    "type": "tabular"
                }
            ],
            "position": {
                "left": 2430,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/snpsift/snpSift_extractFields/4.3+t.galaxy0",
            "tool_shed_repository": {
                "changeset_revision": "5fab4f81391d",
                "name": "snpsift",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"vcf\", \"chromInfo\": \"/opt/galaxy/tool-data/shared/ucsc/chrom/?.len\", \"empty_text\": \".\", \"extract\": \"CHROM POS REF ALT QUAL DP AF SB DP4 EFF[*].IMPACT EFF[*].FUNCLASS EFF[*].EFFECT EFF[*].GENE EFF[*].CODON\", \"input\": null, \"input|__identifier__\": \"SRR11954102\", \"one_effect_per_line\": true, \"separator\": \"\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "4.3+t.galaxy0",
            "type": "tool",
            "uuid": "1350d1df-96d4-4606-b679-08162825cf82",
            "when": null,
            "workflow_outputs": []
        },
        "14": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/nml/collapse_collections/collapse_dataset/5.1.0",
            "errors": null,
            "id": 14,
            "input_connections": {
                "input_list": {
                    "id": 13,
                    "output_name": "output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Collapse Collection",
            "outputs": [
                {
                    "name": "output",
                    "type": "input"
                }
            ],
            "position": {
                "left": 2650,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/nml/collapse_collections/collapse_dataset/5.1.0",
            "tool_shed_repository": {
                "changeset_revision": "90981f86000f",
                "name": "collapse_collections",
                "owner": "nml",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"input\", \"chromInfo\": \"/opt/galaxy/tool-data/shared/ucsc/chrom/?.len\", \"filename\": {\"add_name\": true, \"__current_case__\": 0, \"place_name\": \"same_multiple\"}, \"input_list\": null, \"one_header\": true, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "5.1.0",
            "type": "tool",
            "uuid": "0c53179f-3a40-4add-b702-1fdc7d89a024",
            "when": null,
            "workflow_outputs": []
        }
    },
    "tags": [],
    "uuid": "812c09aa-d77b-4e2f-8864-075ba52979e1",
    "version": 0
}low-NGS data logistics.ga…]()


### NGS data logistics
![image](https://github.com/Eefje-Kuijpers/NGS_Galaxy_workflows/assets/13732259/c56d725a-6bab-476b-a79e-0598eb03fff5)
![image](https://github.com/Eefje-Kuijpers/NGS_Galaxy_workflows/assets/13732259/3cc3f640-d1d8-4d2c-b6ff-8210e57dc8ca)


### Unicycler Assembly
![image](https://github.com/Eefje-Kuijpers/NGS_Galaxy_workflows/assets/13732259/b8a7f394-f5cc-478a-806f-80eb3e69dd24)


### Genome Assembly Quality Control
![image](https://github.com/Eefje-Kuijpers/NGS_Galaxy_workflows/assets/13732259/64763eec-f3fe-4e77-8d63-82d8ed1b09fa)


### Antibiotic resistance detection
![image](https://github.com/Eefje-Kuijpers/NGS_Galaxy_workflows/assets/13732259/34d124d2-6714-411c-922d-67641d714ab2)


### Pathogen detection from (direct Nanopore) sequencing data using Galaxy

