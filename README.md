## FIFO Utility Tool

This repository contains a set of utilities useful to interface with the ST MEMS TAG-based IMUs sensor FIFO: it provides the capability to decode and decompress the data samples.

The APIs are the following:

```
st_fifo_status st_fifo_init(st_fifo_conf *conf);
st_fifo_status st_fifo_decode(st_fifo_out_slot *fifo_out_slot,
                              st_fifo_raw_slot *fifo_raw_slot, uint16_t *out_slot_size, uint16_t stream_size);
void st_fifo_sort(st_fifo_out_slot *fifo_out_slot, uint16_t out_slot_size);
uint16_t st_fifo_get_sensor_occurrence(st_fifo_out_slot *fifo_out_slot,
                                       uint16_t out_slot_size, st_fifo_sensor_type sensor_type);
void st_fifo_extract_sensor(st_fifo_out_slot *sensor_out_slot,
                            st_fifo_out_slot *fifo_out_slot, uint16_t out_slot_size,
                            st_fifo_sensor_type sensor_type);
```

## Repository overview

This repository is structured as follows:  

- [st_fifo.c](./st_fifo.c) It contains the utility code
- [st_fifo.h](./st_fifo.h) It contains the utility data structures and APIs prototypes
- [main.c](./main.c) An application example of how to use the tool APIs
- [makefile](./makefile) It builds it on linux machine.

------

**More information: [http://www.st.com](http://st.com/MEMS)**

**Copyright © 2022 STMicroelectronics**

