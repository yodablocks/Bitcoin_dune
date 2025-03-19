# table: bitcoin.blocks

schema:
| name | type |
| --- | --- |
| time | timestamp |
| height | bigint |
| date | date |
| hash | varbinary |
| bits | varbinary |
| chainwork | varbinary |
| difficulty | double |
| total_fees | double |
| total_reward | double |
| mint_reward | double |
| merkle_root | varbinary |
| transaction_count | bigint |
| nonce | bigint |
| coinbase | varbinary |
| previous_block_hash | varbinary |
| size | bigint |
| stripped_size | bigint |
| version | bigint |
| weight | bigint |

---
# table: bitcoin.inputs

schema:
| name | type |
| --- | --- |
| block_time | timestamp |
| block_date | date |
| block_height | bigint |
| block_hash | varbinary |
| tx_id | varbinary |
| index | integer |
| spent_block_height | bigint |
| spent_tx_id | varbinary |
| spent_output_number | bigint |
| value | double |
| address | varchar |
| type | varchar |
| coinbase | varbinary |
| is_coinbase | boolean |
| script_asm | varchar |
| script_hex | varbinary |
| script_desc | varchar |
| script_signature_asm | varchar |
| script_signature_hex | varbinary |
| sequence | bigint |
| witness_data | array(varbinary) |

---
# table: bitcoin.outputs

schema:
| name | type |
| --- | --- |
| block_time | timestamp |
| block_date | date |
| block_height | bigint |
| block_hash | varbinary |
| tx_id | varbinary |
| index | bigint |
| value | double |
| address | varchar |
| type | varchar |
| script_asm | varchar |
| script_hex | varbinary |

---
# table: bitcoin.transactions

schema:
| name | type |
| --- | --- |
| block_time | timestamp |
| block_date | date |
| block_height | bigint |
| index | integer |
| block_hash | varbinary |
| id | varbinary |
| lock_time | bigint |
| size | bigint |
| virtual_size | bigint |
| coinbase | varbinary |
| is_coinbase | boolean |
| version | bigint |
| input_count | integer |
| output_count | integer |
| input_value | double |
| output_value | double |
| fee | double |
| hex | varbinary |
| input | array(row(value double,coinbase varbinary,height bigint,tx_id varbinary,output_number bigint,script_pub_key row(address varchar,asm varchar,desc varchar,hex varbinary,type varchar),script_signature row(asm varchar,hex varbinary),sequence bigint,witness_data array(varbinary))) |
| output | array(row(index bigint,script_pub_key row(address varchar,asm varchar,desc varchar,hex varbinary,type varchar),value double)) |
