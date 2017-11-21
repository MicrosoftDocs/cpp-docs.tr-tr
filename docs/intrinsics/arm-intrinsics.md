---
title: "ARM iç bilgileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- arm_neon/vsetq_lane_p8
- armintr/_arm_uxtb
- arm_neon/vld4_lane_p8
- arm_neon/vrshrn_n_s64
- arm_neon/vsli_n_u32
- arm_neon/vsraq_n_u16
- arm_neon/vcgt_f32
- armintr/__iso_volatile_store32
- arm_neon/vceqq_f32
- armintr/_arm_smlal
- arm_neon/vmull_n_s32
- arm_neon/vmax_s8
- arm_neon/vmvn_u32
- arm_neon/vrshl_u32
- arm_neon/int32x2_t
- arm_neon/vdupq_n_p8
- arm_neon/vpmax_u16
- arm_neon/vtrnq_s32
- arm_neon/vset_lane_f32
- arm_neon/vrev64_s8
- arm_neon/vtrnq_p8
- arm_neon/vqshlq_u64
- arm_neon/vld1q_dup_s64
- arm_neon/vmovq_n_u64
- arm_neon/vqshrn_n_u16
- arm_neon/vhadd_s32
- arm_neon/vrhaddq_u32
- arm_neon/vst1q_p8
- arm_neon/vshrn_n_s16
- arm_neon/vget_high_f32
- arm_neon/vuzpq_s16
- arm_neon/vand_u16
- arm_neon/vmulq_s32
- arm_neon/vrsraq_n_s64
- arm_neon/vceqq_s8
- arm_neon/uint64x1x3_t
- arm_neon/veor_u32
- armintr/_arm_pkhtb
- arm_neon/vorrq_u16
- arm_neon/vpaddl_s8
- arm_neon/vmla_n_s16
- arm_neon/vqdmlal_lane_s32
- arm_neon/vshlq_n_u8
- arm_neon/vst2_lane_p8
- arm_neon/vld3q_u16
- arm_neon/vandq_u8
- arm_neon/vst1_u64
- arm_neon/vaddq_s64
- arm_neon/vuzpq_u32
- arm_neon/vld3_lane_p8
- arm_neon/vminq_s32
- arm_neon/vabd_u16
- arm_neon/vdup_n_u32
- arm_neon/vmul_p8
- arm_neon/vsra_n_u16
- arm_neon/vst3q_u16
- arm_neon/int32x2x3_t
- arm_neon/vld2_dup_u16
- arm_neon/vrhaddq_u8
- arm_neon/vhadd_u8
- arm_neon/vgetq_lane_s32
- arm_neon/vcleq_u16
- arm_neon/vabdq_s8
- arm_neon/vrev16q_u8
- arm_neon/vqshlu_n_s64
- arm_neon/vcvt_n_s32_f32
- arm_neon/vqrshrn_n_s64
- arm_neon/vst1q_p16
- arm_neon/vgetq_lane_s16
- arm_neon/vtstq_u32
- arm_neon/vmlsl_n_s16
- arm_neon/vcge_s8
- arm_neon/vshr_n_s16
- armintr/_arm_rbit
- arm_neon/vmls_u32
- arm_neon/vmls_lane_u32
- arm_neon/vcvtq_n_s32_f32
- arm_neon/vqshl_n_s8
- arm_neon/vst1q_s16
- armintr/__emit
- arm_neon/vshlq_s64
- arm_neon/vuzp_s8
- arm_neon/vld1q_lane_s64
- arm_neon/veorq_s32
- arm_neon/vaddq_u64
- arm_neon/vceq_s32
- arm_neon/vmovn_u16
- arm_neon/vabal_s8
- arm_neon/vabsq_f32
- armintr/_arm_smuad
- arm_neon/veor_u8
- arm_neon/int16x4_t
- arm_neon/vsraq_n_s16
- arm_neon/vshlq_s8
- arm_neon/vcreate_u32
- arm_neon/vzipq_s8
- arm_neon/vst3q_u8
- arm_neon/int64x1x4_t
- armintr/__iso_volatile_store16
- arm_neon/vst4_lane_p16
- arm_neon/vld1_dup_p16
- arm_neon/vhadd_s16
- arm_neon/vtbl2_s8
- arm_neon/veorq_u32
- arm_neon/vqdmlal_lane_s16
- arm_neon/vrsra_n_u8
- arm_neon/vbslq_u16
- arm_neon/vget_low_s64
- arm_neon/vceq_u16
- arm_neon/vdupq_lane_u32
- arm_neon/vabdl_u32
- arm_neon/vmlal_s32
- arm_neon/vst1_lane_u8
- arm_neon/vld4q_f16
- arm_neon/vqdmlsl_s32
- arm_neon/vqrdmulh_s32
- arm_neon/vqrshl_u8
- arm_neon/uint32x4x4_t
- arm_neon/vabaq_u16
- arm_neon/vcnt_p8
- arm_neon/vld3q_s16
- arm_neon/vshl_n_u32
- arm_neon/vrev64q_u16
- arm_neon/vextq_s64
- arm_neon/vhsubq_s8
- arm_neon/vld2_dup_u8
- arm_neon/vst3_s16
- arm_neon/vorn_u16
- arm_neon/vst4_f16
- arm_neon/vpadalq_u8
- armintr/__iso_volatile_load8
- arm_neon/vmovl_u16
- arm_neon/vld4q_u32
- arm_neon/vcgt_u32
- arm_neon/vmlaq_n_u32
- arm_neon/vrsra_n_u64
- arm_neon/vst4_s8
- arm_neon/vcvtq_n_f32_u32
- arm_neon/vst2q_u16
- arm_neon/vqshrn_n_s16
- arm_neon/vld4_s16
- arm_neon/uint16x8x4_t
- arm_neon/vrsqrte_u32
- arm_neon/vcltq_s8
- arm_neon/vst3_u16
- arm_neon/vst2_f32
- arm_neon/vld2_u64
- arm_neon/vst1_u16
- arm_neon/vmls_s16
- arm_neon/vqrshlq_s32
- arm_neon/vqdmull_s16
- arm_neon/vld2_lane_p16
- arm_neon/vpaddlq_u8
- arm_neon/vcvt_n_f32_u32
- arm_neon/vcgtq_u8
- arm_neon/vshl_s32
- arm_neon/vtbx3_p8
- arm_neon/vld3_dup_s32
- arm_neon/int16x4x3_t
- arm_neon/vcale_f32
- arm_neon/vqabsq_s32
- arm_neon/vmulq_u16
- arm_neon/vst1_s8
- arm_neon/vclt_u8
- armintr/_arm_sxtb16
- arm_neon/vshr_n_s8
- arm_neon/vst1_lane_f16
- arm_neon/vorn_s64
- armintr/_arm_usub8
- arm_neon/vst4_lane_f32
- arm_neon/vmls_lane_u16
- arm_neon/vpaddl_u32
- arm_neon/vdup_lane_u64
- arm_neon/vsri_n_p16
- arm_neon/vqrshlq_u64
- arm_neon/vclz_s16
- arm_neon/vsra_n_u32
- arm_neon/vabaq_s8
- arm_neon/vst2_lane_s8
- arm_neon/vcvt_n_u32_f32
- arm_neon/vst3_u32
- arm_neon/vcvtq_f32_u32
- arm_neon/vraddhn_s64
- armintr/_arm_uqsax
- arm_neon/vshl_u8
- armintr/_arm_uqadd16
- arm_neon/vrsra_n_u16
- arm_neon/vrshl_u64
- arm_neon/int32x4x3_t
- arm_neon/vmull_u8
- arm_neon/vcombine_u64
- arm_neon/vmull_u16
- arm_neon/vld1_dup_s8
- armintr/_CountLeadingSigns64
- arm_neon/vqshlq_n_s32
- arm_neon/vrecpe_f32
- arm_neon/vsri_n_u32
- arm_neon/vrsraq_n_s8
- arm_neon/vsetq_lane_s16
- arm_neon/vget_high_u32
- arm_neon/vmlal_u32
- arm_neon/vdupq_lane_s16
- arm_neon/vsubq_u64
- arm_neon/vext_p8
- arm_neon/vshl_u16
- arm_neon/vmls_n_u16
- arm_neon/vmull_s16
- arm_neon/vmovq_n_s64
- arm_neon/vaddq_f32
- arm_neon/vshl_n_s16
- arm_neon/vext_p16
- arm_neon/vextq_u32
- arm_neon/vld1_p8
- arm_neon/veor_s32
- arm_neon/int16x8x4_t
- arm_neon/vst1q_u16
- arm_neon/vzipq_p8
- arm_neon/int32x4x4_t
- arm_neon/vqdmulhq_lane_s32
- arm_neon/vst3_lane_u32
- arm_neon/vhsubq_s32
- armintr/__static_assert
- arm_neon/vst3q_lane_u16
- arm_neon/vpmin_u32
- arm_neon/vrev64q_p16
- arm_neon/vcleq_f32
- arm_neon/vhsub_u16
- arm_neon/vld2_lane_s32
- arm_neon/vmlsl_s32
- armintr/_arm_rev
- arm_neon/vcgeq_s16
- arm_neon/vmulq_s8
- arm_neon/vsri_n_s8
- arm_neon/vpadd_f32
- arm_neon/vld1q_lane_f16
- arm_neon/vmls_u16
- arm_neon/vld1_lane_f32
- arm_neon/vmlaq_lane_s16
- arm_neon/vqadd_u32
- arm_neon/vmul_n_s32
- arm_neon/vld1q_dup_p8
- arm_neon/vtrnq_s8
- arm_neon/vbslq_p8
- arm_neon/vget_lane_s8
- arm_neon/vext_u16
- arm_neon/vsubq_s16
- arm_neon/vld4_lane_s8
- arm_neon/uint32x2x2_t
- arm_neon/vdup_n_s8
- arm_neon/vld4_lane_u16
- arm_neon/vmovq_n_s16
- arm_neon/vst4q_s32
- arm_neon/vst2q_f16
- arm_neon/vbslq_s16
- arm_neon/vand_u64
- arm_neon/poly16_t
- arm_neon/vaba_u16
- arm_neon/vqshlq_s64
- armintr/_arm_uxth
- arm_neon/vst2_lane_s16
- arm_neon/vand_u8
- arm_neon/int8x16x3_t
- arm_neon/vrev64_u16
- arm_neon/vld2_lane_s16
- arm_neon/vabaq_s16
- arm_neon/vsli_n_u8
- arm_neon/vsraq_n_u64
- arm_neon/vmlsl_s16
- arm_neon/vmovn_u64
- arm_neon/vld4_f32
- arm_neon/vst2q_f32
- arm_neon/vtbx3_u8
- arm_neon/vcombine_s8
- arm_neon/vqdmulhq_s32
- arm_neon/vgetq_lane_p8
- armintr/_arm_smusd
- arm_neon/vpmax_u32
- arm_neon/vceq_f32
- arm_neon/vsri_n_p8
- arm_neon/vhsubq_u8
- arm_neon/vuzp_s16
- arm_neon/uint32x2x4_t
- arm_neon/vst4_lane_s32
- arm_neon/vsli_n_p8
- arm_neon/vld3_lane_f16
- arm_neon/vbic_u64
- arm_neon/vmlal_u16
- arm_neon/vmvn_s8
- arm_neon/vtstq_s8
- arm_neon/vmaxq_s32
- arm_neon/vqmovn_u64
- armintr/_arm_ssax
- arm_neon/vext_u32
- arm_neon/vld1_dup_u64
- arm_neon/vmlal_n_s16
- armintr/_arm_smulbb
- arm_neon/vqrdmulhq_lane_s16
- arm_neon/vdup_n_p8
- arm_neon/vaba_s8
- arm_neon/vrshrq_n_s32
- arm_neon/vmvnq_s32
- arm_neon/vpadal_s32
- arm_neon/vqshl_s16
- arm_neon/vtrn_p8
- arm_neon/vzip_s16
- arm_neon/vcge_f32
- armintr/_arm_sxtab16
- arm_neon/vst1q_lane_u64
- arm_neon/vqrshlq_u16
- arm_neon/int8x8_t
- arm_neon/vorr_u8
- arm_neon/vrev64_f32
- arm_neon/vpaddlq_s16
- arm_neon/vdupq_lane_u64
- arm_neon/vcltq_u16
- arm_neon/vst3_lane_f32
- arm_neon/vld2_dup_f32
- armintr/_arm_smmul
- arm_neon/vbsl_s16
- arm_neon/vld1_lane_u8
- arm_neon/vld2q_lane_u16
- arm_neon/vqshlu_n_s32
- armintr/_arm_smlalbt
- arm_neon/vmla_s8
- arm_neon/vsli_n_p16
- arm_neon/vmla_u8
- arm_neon/vqaddq_s16
- arm_neon/vld3_p16
- arm_neon/uint64x2x4_t
- arm_neon/vcnt_u8
- arm_neon/vcltq_u8
- arm_neon/vtbx1_p8
- arm_neon/vrev32q_u16
- arm_neon/vld1_lane_u16
- arm_neon/vqadd_s16
- arm_neon/vcnt_s8
- armintr/_MulUnsignedHigh
- arm_neon/vsliq_n_u8
- arm_neon/vpmin_s16
- armintr/__iso_volatile_load16
- arm_neon/vst2_lane_f32
- arm_neon/vqsubq_s32
- arm_neon/vqshl_s32
- arm_neon/vsraq_n_u32
- arm_neon/vcreate_s32
- arm_neon/vld3q_lane_u32
- arm_neon/vaddq_u16
- arm_neon/vand_s32
- arm_neon/vbicq_s32
- armintr/_arm_smulbt
- arm_neon/vrsra_n_s8
- arm_neon/vshrq_n_u32
- arm_neon/vld4_f16
- arm_neon/vcagtq_f32
- arm_neon/vaddw_u32
- armintr/_arm_uxtah
- arm_neon/vtstq_u8
- arm_neon/vld1_dup_u16
- arm_neon/int16x4x4_t
- arm_neon/vqshluq_n_s8
- arm_neon/vqdmulhq_n_s32
- arm_neon/vst1_s64
- arm_neon/vrsubhn_u16
- arm_neon/vld4_dup_p16
- arm_neon/vmlaq_s32
- arm_neon/vnegq_s32
- arm_neon/vst2q_u8
- arm_neon/vget_low_s32
- arm_neon/vorn_u32
- arm_neon/vld1q_s8
- arm_neon/vandq_s64
- arm_neon/vmvn_p8
- arm_neon/vabdl_s16
- arm_neon/vqshl_u32
- arm_neon/vld3_dup_u16
- arm_neon/vmov_n_f32
- arm_neon/vcvt_f32_u32
- arm_neon/vrhadd_s8
- arm_neon/vpadal_u32
- armintr/_arm_ubfx
- arm_neon/vcgt_s8
- arm_neon/vget_lane_f32
- arm_neon/vcge_s16
- arm_neon/vmov_n_s64
- arm_neon/vmulq_n_f32
- arm_neon/vpadalq_u32
- armintr/_arm_smlaldx
- arm_neon/vtst_u16
- arm_neon/vmls_n_s16
- arm_neon/vcombine_f32
- arm_neon/vld1q_p16
- armintr/_arm_ssat
- arm_neon/vextq_s8
- arm_neon/vmax_u32
- arm_neon/vqsubq_s64
- arm_neon/vcltq_s16
- arm_neon/vst2q_s8
- arm_neon/vpmax_u8
- arm_neon/vld4_dup_p8
- arm_neon/vrshr_n_u64
- arm_neon/vqrshrun_n_s16
- arm_neon/vget_low_u64
- arm_neon/vst2q_s32
- arm_neon/vst4_s32
- arm_neon/vrshrq_n_u8
- arm_neon/vdupq_n_u64
- arm_neon/vsriq_n_u8
- arm_neon/vdupq_lane_u8
- arm_neon/vsriq_n_s64
- arm_neon/vget_low_u8
- arm_neon/vst1_lane_p16
- arm_neon/vld1q_lane_u8
- arm_neon/vcgt_s32
- arm_neon/vst1_lane_u32
- arm_neon/vzipq_p16
- arm_neon/vmvn_u16
- arm_neon/vld1q_lane_u16
- armintr/_MoveToCoprocessor64
- arm_neon/vdup_n_u16
- arm_neon/vzipq_f32
- arm_neon/vshl_s16
- arm_neon/vmlaq_n_s16
- arm_neon/vget_lane_s64
- arm_neon/vld1q_lane_f32
- arm_neon/vnegq_s16
- armintr/_arm_usax
- arm_neon/vabd_s16
- arm_neon/vmovq_n_u32
- arm_neon/vshlq_n_u16
- armintr/_CountLeadingSigns
- arm_neon/vld3q_f16
- arm_neon/vceqq_u32
- arm_neon/int8x8x2_t
- arm_neon/vst2_s64
- arm_neon/vst4q_lane_s16
- arm_neon/vorn_s32
- arm_neon/vcle_f32
- arm_neon/vld1_p16
- arm_neon/vtrn_u32
- arm_neon/vbsl_s32
- arm_neon/float32x2_t
- arm_neon/vmvn_s32
- arm_neon/vqdmlsl_lane_s16
- arm_neon/vtbl3_s8
- arm_neon/vsra_n_u8
- arm_neon/vcvtq_u32_f32
- arm_neon/vst1_p8
- arm_neon/vrev64_p16
- armintr/__ldrexd
- arm_neon/vcgeq_u8
- arm_neon/vmlal_n_s32
- arm_neon/vst1q_lane_p8
- arm_neon/vpadalq_s32
- arm_neon/vtstq_p8
- arm_neon/vld4_lane_u8
- armintr/_arm_ssub16
- arm_neon/vpaddlq_u16
- armintr/_arm_udiv
- arm_neon/vld1_lane_p8
- arm_neon/vst1q_u32
- arm_neon/vld1_f32
- arm_neon/uint64x2x2_t
- arm_neon/vqsubq_u64
- arm_neon/vld4q_s32
- arm_neon/vceq_s16
- arm_neon/vst3_s64
- arm_neon/vext_s8
- armintr/_arm_smlsd
- arm_neon/vpadal_s16
- arm_neon/vbic_s32
- arm_neon/vld1_dup_u8
- arm_neon/vclt_f32
- arm_neon/vrev64_s16
- arm_neon/vrshlq_s64
- arm_neon/vdupq_n_s64
- arm_neon/vuzp_p16
- arm_neon/vld3_dup_p16
- arm_neon/vcreate_s8
- armintr/_arm_smlatt
- arm_neon/vtst_s32
- arm_neon/vshrq_n_s64
- arm_neon/vqshlq_n_s64
- arm_neon/vqshlu_n_s16
- arm_neon/vcleq_s16
- arm_neon/vmull_lane_s16
- arm_neon/int32x4_t
- arm_neon/vqadd_s8
- arm_neon/vld2q_f16
- arm_neon/vld2q_lane_p16
- arm_neon/vadd_u32
- arm_neon/vcntq_u8
- arm_neon/vst1_f32
- arm_neon/vmaxq_u32
- arm_neon/vsub_u64
- arm_neon/vsubl_s32
- arm_neon/poly16x4_t
- arm_neon/vgetq_lane_u16
- arm_neon/vdup_lane_s32
- arm_neon/vrhadd_s32
- arm_neon/veorq_u8
- arm_neon/vclzq_s8
- arm_neon/vsliq_n_s64
- arm_neon/vpadalq_s16
- arm_neon/vmla_n_f32
- arm_neon/vcgt_u16
- armintr/_arm_usada8
- arm_neon/vabd_u32
- arm_neon/vgetq_lane_s8
- arm_neon/vqshlq_n_u64
- arm_neon/vabaq_u32
- armintr/_arm_uhsax
- arm_neon/vmulq_f32
- arm_neon/vld3_dup_s16
- arm_neon/vst3_f16
- arm_neon/vrshrq_n_s64
- armintr/__rdpmccntr64
- arm_neon/vclsq_s32
- arm_neon/vmax_u16
- arm_neon/vmvnq_p8
- arm_neon/veor_u16
- arm_neon/vqshrn_n_u32
- arm_neon/vextq_u64
- arm_neon/vld1q_f32
- arm_neon/vget_low_u32
- arm_neon/vhaddq_s32
- arm_neon/vminq_u16
- arm_neon/vqrdmulhq_lane_s32
- arm_neon/vmla_s16
- arm_neon/vadd_s16
- arm_neon/vbsl_u16
- arm_neon/vhsub_s8
- arm_neon/vld4q_lane_p16
- arm_neon/vld1_s16
- arm_neon/vst2q_lane_p16
- arm_neon/vld2_dup_s8
- arm_neon/vst3q_s16
- arm_neon/vcgeq_u32
- arm_neon/vabdq_s16
- arm_neon/vrhadd_u16
- arm_neon/vqshlq_n_u32
- arm_neon/vst4q_lane_u32
- arm_neon/vrsraq_n_u64
- arm_neon/vmlsq_n_s32
- arm_neon/vld4_u8
- arm_neon/vld2_f16
- arm_neon/vqshlq_u8
- arm_neon/vorrq_u64
- arm_neon/vmin_u16
- arm_neon/vext_u8
- arm_neon/vpaddl_s32
- arm_neon/vshlq_u64
- arm_neon/vst2q_lane_f16
- armintr/_arm_sbfx
- arm_neon/vld3_dup_f16
- armintr/_arm_uhasx
- arm_neon/vst2_lane_u8
- armintr/_arm_smultb
- arm_neon/vdup_n_p16
- arm_neon/vtrnq_u32
- arm_neon/vrshlq_u8
- arm_neon/vld4_lane_p16
- arm_neon/vsraq_n_s32
- arm_neon/vclt_s16
- arm_neon/vzip_u8
- arm_neon/vld3_lane_s16
- arm_neon/vceqq_s32
- arm_neon/vld3_dup_f32
- arm_neon/vld4q_lane_s32
- arm_neon/poly8x16x4_t
- arm_neon/uint64x1x2_t
- arm_neon/vqdmlal_n_s16
- arm_neon/vld2_dup_f16
- arm_neon/vshrq_n_s32
- arm_neon/vcleq_s8
- arm_neon/vld3_s32
- arm_neon/vqrshlq_s64
- arm_neon/vbsl_f32
- arm_neon/vext_s64
- arm_neon/vabaq_s32
- arm_neon/vmulq_s16
- arm_neon/vld3_lane_u16
- arm_neon/vld3q_lane_u16
- armintr/_arm_smlaltt
- arm_neon/poly8x8x2_t
- arm_neon/vst3q_u32
- armintr/_arm_smlsdx
- arm_neon/vqrshl_s64
- arm_neon/vextq_p8
- armintr/_arm_uhsub16
- arm_neon/vld3q_p8
- armintr/_arm_smlawt
- armintr/_arm_smlawb
- arm_neon/vdupq_lane_s8
- arm_neon/vaddl_s16
- arm_neon/vcombine_p16
- arm_neon/vzipq_u32
- arm_neon/poly16x8_t
- arm_neon/vshlq_n_s32
- arm_neon/vrshl_s8
- arm_neon/vst2_u64
- arm_neon/vrev64q_s8
- arm_neon/vst2q_lane_s32
- arm_neon/vld2_dup_s16
- arm_neon/vclt_u16
- arm_neon/vuzp_p8
- arm_neon/vshrq_n_s16
- arm_neon/vst3_u64
- arm_neon/vpmin_u16
- arm_neon/vld3q_lane_s32
- arm_neon/vmlal_s16
- arm_neon/poly16x4x4_t
- arm_neon/vorr_u16
- arm_neon/vsliq_n_s16
- arm_neon/vaddl_u8
- arm_neon/vld4_dup_s32
- arm_neon/vld2_f32
- arm_neon/vclt_u32
- arm_neon/vmull_lane_u16
- arm_neon/vsubw_u32
- arm_neon/vld2_dup_s32
- arm_neon/vuzp_s32
- arm_neon/vcge_s32
- arm_neon/vdup_lane_p16
- arm_neon/vpmin_s8
- arm_neon/vpaddlq_u32
- arm_neon/vmlaq_n_s32
- arm_neon/vshrn_n_u64
- arm_neon/vrshr_n_u16
- arm_neon/vld1_s64
- arm_neon/vbsl_u64
- armintr/_arm_smlad
- arm_neon/vqsub_s16
- arm_neon/vld4_p8
- arm_neon/vqdmulh_lane_s32
- arm_neon/vld3_dup_s64
- arm_neon/vornq_s32
- arm_neon/vpadd_u8
- arm_neon/vld3_lane_p16
- arm_neon/uint64x1x4_t
- arm_neon/vld3_u16
- armintr/_arm_shsax
- arm_neon/vabdq_u16
- arm_neon/vcgtq_f32
- arm_neon/vsubq_s8
- arm_neon/vget_low_f16
- arm_neon/vld4_dup_u64
- arm_neon/vst3_lane_s8
- armintr/_arm_ssat16
- arm_neon/vmlaq_f32
- arm_neon/vsri_n_s32
- arm_neon/vmax_u8
- arm_neon/vqadd_u8
- armintr/_arm_uqsub8
- armintr/_arm_clz
- arm_neon/vcgtq_s32
- arm_neon/vraddhn_s32
- arm_neon/vzip_s8
- arm_neon/veorq_s16
- arm_neon/vsetq_lane_s32
- arm_neon/vmul_n_u16
- armintr/_ReadBankedReg
- arm_neon/vld1q_u8
- arm_neon/vld4_p16
- arm_neon/int64x2x2_t
- arm_neon/vmaxq_s8
- arm_neon/vpmax_s16
- arm_neon/vshlq_u16
- arm_neon/vtrnq_p16
- arm_neon/vabal_u16
- arm_neon/vld2_lane_u16
- arm_neon/vrev32_u8
- arm_neon/vrshl_s32
- arm_neon/vget_low_f32
- arm_neon/vld2_s8
- arm_neon/vclzq_s16
- arm_neon/vqdmulhq_n_s16
- arm_neon/vset_lane_u64
- arm_neon/vld2_dup_p16
- arm_neon/vpaddlq_s32
- arm_neon/vld2q_p8
- arm_neon/vst3_lane_u8
- arm_neon/vld4_dup_f32
- arm_neon/vld2_s64
- arm_neon/vmls_u8
- arm_neon/vtbx4_u8
- arm_neon/vsetq_lane_f32
- arm_neon/vcvt_s32_f32
- arm_neon/vst3q_s32
- arm_neon/vmlsq_s8
- arm_neon/vmlaq_n_u16
- armintr/__iso_volatile_load64
- arm_neon/vcgt_u8
- arm_neon/vld2_dup_p8
- arm_neon/vmov_n_u8
- armintr/_arm_sasx
- arm_neon/vmovq_n_p16
- arm_neon/vmlaq_u32
- arm_neon/vst3_f32
- arm_neon/int32x2x4_t
- arm_neon/vld1q_lane_u64
- arm_neon/vclz_u16
- arm_neon/uint8x8_t
- arm_neon/vsub_u32
- arm_neon/vorn_u8
- armintr/__wfe
- arm_neon/vget_high_s16
- arm_neon/vzip_p8
- arm_neon/vmlal_lane_s16
- arm_neon/vmulq_u8
- armintr/_isunordered
- arm_neon/vld1_dup_f32
- arm_neon/vld4_lane_s16
- arm_neon/vdupq_n_s16
- arm_neon/vst3q_p16
- arm_neon/vst1_lane_f32
- arm_neon/float32x4x3_t
- arm_neon/vand_s8
- arm_neon/float32x2x4_t
- arm_neon/vld3_p8
- arm_neon/vmlaq_lane_u16
- armintr/_arm_uqsub16
- arm_neon/vget_high_s32
- arm_neon/vshl_n_s32
- arm_neon/vornq_s8
- arm_neon/vmlsl_n_u32
- arm_neon/vqshlq_n_s8
- arm_neon/int32x2x2_t
- arm_neon/int16x4x2_t
- arm_neon/vceqq_u8
- arm_neon/vcreate_f16
- arm_neon/vorn_s16
- arm_neon/vqmovn_s32
- arm_neon/vextq_u8
- arm_neon/vld4_s32
- armintr/_WriteStatusReg
- arm_neon/uint8x16_t
- arm_neon/vshrn_n_s64
- arm_neon/vmul_n_u32
- arm_neon/vabdl_u8
- arm_neon/vtbx3_s8
- arm_neon/vaddhn_s16
- arm_neon/vld3q_s8
- arm_neon/vmlsl_n_u16
- arm_neon/vrev64q_s32
- arm_neon/int16x8_t
- arm_neon/vext_s32
- arm_neon/vdupq_n_f32
- arm_neon/vld1q_lane_s32
- arm_neon/vqrshlq_u32
- arm_neon/vtbl2_u8
- arm_neon/vgetq_lane_u8
- arm_neon/veorq_u64
- arm_neon/vcntq_s8
- arm_neon/vbslq_p16
- arm_neon/vqnegq_s32
- arm_neon/vaddw_s32
- arm_neon/vmov_n_p8
- arm_neon/vmull_p8
- arm_neon/vld1_lane_u32
- arm_neon/vcombine_s16
- arm_neon/vqshrn_n_s64
- arm_neon/vceqq_s16
- arm_neon/vld4q_p16
- armintr/_ReadStatusReg
- armintr/_arm_qdadd
- arm_neon/uint32x4x2_t
- arm_neon/vcleq_u8
- armintr/_arm_sxtah
- arm_neon/vrhaddq_s32
- arm_neon/vset_lane_s64
- arm_neon/vld4_s64
- armintr/_DAddSatInt
- arm_neon/vorr_s8
- arm_neon/vst2_u32
- arm_neon/vshll_n_u16
- arm_neon/vld2_dup_u32
- arm_neon/vst3q_lane_s32
- arm_neon/vst3q_p8
- armintr/_MoveFromCoprocessor
- arm_neon/uint32x4_t
- arm_neon/vuzpq_s8
- arm_neon/vrecps_f32
- arm_neon/vst1_lane_s8
- arm_neon/vtbx1_s8
- arm_neon/uint16x8x3_t
- arm_neon/vpaddl_s16
- arm_neon/vsubq_s64
- arm_neon/vrsraq_n_u8
- arm_neon/vqadd_s64
- arm_neon/vst4_lane_s16
- arm_neon/vqadd_u16
- arm_neon/vset_lane_u32
- arm_neon/vand_u32
- arm_neon/vrsqrtsq_f32
- arm_neon/vqaddq_u32
- arm_neon/vsra_n_s64
- armintr/_arm_umlal
- arm_neon/vcvt_f32_f16
- arm_neon/vget_lane_u32
- arm_neon/vbsl_s8
- arm_neon/vrshlq_u32
- arm_neon/vqdmull_lane_s16
- arm_neon/vabsq_s32
- arm_neon/vld3_s8
- arm_neon/vst3q_lane_s16
- arm_neon/vld2q_lane_s16
- arm_neon/vst1_lane_s64
- arm_neon/vmov_n_u16
- arm_neon/vst4_lane_u8
- arm_neon/vshll_n_u32
- arm_neon/vqabs_s8
- arm_neon/vmvnq_u8
- arm_neon/vpadalq_u16
- arm_neon/vbsl_p16
- arm_neon/vqrshrn_n_u16
- arm_neon/vld3q_u32
- arm_neon/vcgeq_f32
- armintr/__iso_volatile_load32
- arm_neon/vrecpe_u32
- arm_neon/vld2_dup_u64
- arm_neon/vld3q_f32
- armintr/_arm_shsub8
- arm_neon/vdup_lane_s64
- arm_neon/vqrshl_s8
- arm_neon/vsliq_n_u16
- arm_neon/vld1q_u16
- arm_neon/vorr_u32
- arm_neon/vqrshl_s32
- armintr/__dmb
- arm_neon/veorq_s8
- arm_neon/vld1_u16
- arm_neon/vmov_n_u32
- arm_neon/vhsub_s16
- arm_neon/vst4q_lane_u16
- arm_neon/vbsl_u8
- armintr/_arm_uxtab
- arm_neon/vld2q_lane_f32
- arm_neon/vst2_p8
- armintr/_arm_smmla
- arm_neon/vaddw_u16
- arm_neon/vmlal_s8
- arm_neon/vtst_u32
- arm_neon/vtbl4_u8
- arm_neon/vcvt_n_f32_s32
- arm_neon/vcageq_f32
- arm_neon/vget_low_s16
- arm_neon/vdupq_n_u8
- arm_neon/vorn_s8
- arm_neon/uint8x16x3_t
- arm_neon/vabdq_u32
- arm_neon/vrev64_p8
- arm_neon/vqsubq_s8
- armintr/_arm_smlabb
- arm_neon/vbicq_s64
- arm_neon/vmaxq_u16
- arm_neon/vdup_n_u8
- arm_neon/veor_s8
- arm_neon/int16x8x2_t
- arm_neon/vcvtq_s32_f32
- arm_neon/vtrn_u16
- arm_neon/vbslq_s32
- arm_neon/vld1q_dup_u32
- arm_neon/vmul_n_f32
- arm_neon/vqrshl_u32
- arm_neon/vqsubq_s16
- arm_neon/vst2_lane_f16
- armintr/_arm_smulwt
- arm_neon/vrshrn_n_u32
- arm_neon/vget_high_p16
- arm_neon/vqadd_u64
- arm_neon/vsli_n_s32
- arm_neon/vhadd_u32
- arm_neon/vmlsl_lane_u16
- arm_neon/vclzq_u32
- arm_neon/vqshrun_n_s64
- arm_neon/vrev64q_u32
- arm_neon/vqshrun_n_s16
- arm_neon/vrev32q_s8
- armintr/_arm_shasx
- arm_neon/vaddl_s8
- armintr/_arm_smull
- arm_neon/vabaq_u8
- armintr/_arm_revsh
- arm_neon/vsubq_f32
- arm_neon/poly16x4x2_t
- arm_neon/poly8x8x3_t
- arm_neon/vsubhn_s64
- arm_neon/vcle_u16
- arm_neon/poly8x16x3_t
- arm_neon/vqdmlsl_n_s16
- arm_neon/vqshl_u64
- arm_neon/vcge_u16
- armintr/_arm_uasx
- arm_neon/vmovl_s32
- arm_neon/vst1q_lane_u16
- arm_neon/vbic_u32
- arm_neon/vld2_s16
- armintr/_arm_qasx
- arm_neon/vorrq_u8
- arm_neon/vst2_s32
- armintr/_WriteBankedReg
- arm_neon/veorq_s64
- arm_neon/vld4_lane_f32
- arm_neon/vcreate_u8
- arm_neon/vset_lane_u8
- arm_neon/vandq_u16
- arm_neon/vrsubhn_s64
- arm_neon/vst1q_lane_p16
- arm_neon/uint8x8x2_t
- arm_neon/vmlsl_s8
- arm_neon/vmax_s32
- arm_neon/uint32x4x3_t
- arm_neon/vld4_dup_u16
- arm_neon/vabs_s32
- arm_neon/vld3_dup_u32
- arm_neon/vrshl_u16
- arm_neon/vcle_u8
- arm_neon/vqshl_n_u16
- arm_neon/vbic_s8
- arm_neon/float32x4x2_t
- arm_neon/vmls_f32
- arm_neon/vshll_n_u8
- arm_neon/vminq_s8
- arm_neon/vmlsq_lane_f32
- arm_neon/vst1q_f16
- arm_neon/vst1_lane_u64
- arm_neon/vrhadd_u8
- arm_neon/vclt_s32
- arm_neon/vst2_p16
- arm_neon/vrshrq_n_u16
- arm_neon/vneg_s32
- arm_neon/vmovl_s16
- arm_neon/vqshlq_s8
- arm_neon/vld1_s8
- arm_neon/vqdmulh_s32
- arm_neon/vcls_s8
- armintr/__trap
- arm_neon/vuzp_u32
- armintr/_CopyInt64FromDouble
- arm_neon/int8x16x2_t
- arm_neon/vmovn_s32
- arm_neon/vget_high_s8
- arm_neon/veor_s64
- armintr/_arm_uadd8
- arm_neon/vrev16_u8
- arm_neon/vbicq_u64
- arm_neon/vst4_lane_f16
- arm_neon/vst3_s32
- arm_neon/poly8x8_t
- arm_neon/vtstq_u16
- arm_neon/vld1_lane_s8
- arm_neon/float32x4x4_t
- arm_neon/vst2_s16
- arm_neon/vqrdmulhq_s32
- arm_neon/vqdmulhq_s16
- arm_neon/vrshrq_n_s8
- arm_neon/vcle_s32
- arm_neon/vtbl3_p8
- arm_neon/vbslq_u8
- arm_neon/vst4_u64
- armintr/_arm_umaal
- arm_neon/vshll_n_s8
- arm_neon/vcvt_u32_f32
- arm_neon/vld4q_p8
- arm_neon/vsetq_lane_u16
- arm_neon/vabd_u8
- arm_neon/vclz_u8
- arm_neon/vsubq_u32
- arm_neon/vld1q_lane_p16
- arm_neon/vcgtq_s16
- arm_neon/vmla_lane_s32
- arm_neon/vshlq_n_s64
- arm_neon/vbsl_u32
- arm_neon/vqshlq_s16
- armintr/_arm_qadd8
- arm_neon/vrshr_n_s32
- armintr/_CountOneBits64
- arm_neon/vceq_u32
- arm_neon/vbsl_p8
- arm_neon/uint16x8x2_t
- arm_neon/vsli_n_s16
- arm_neon/vmla_n_s32
- arm_neon/vld4_dup_u32
- arm_neon/vshrq_n_s8
- arm_neon/vqaddq_s8
- arm_neon/vshl_n_u64
- arm_neon/vtbl2_p8
- arm_neon/vcleq_u32
- arm_neon/vqsub_u32
- arm_neon/vmovl_u8
- arm_neon/vmlal_u8
- arm_neon/vmul_s8
- armintr/_MoveFromCoprocessor64
- arm_neon/vrsraq_n_s16
- arm_neon/vdupq_n_u32
- arm_neon/vmov_n_s16
- arm_neon/vst4_lane_p8
- arm_neon/vld1_s32
- arm_neon/vst4_p8
- arm_neon/vsriq_n_u32
- arm_neon/vqdmull_n_s16
- arm_neon/vshlq_u32
- arm_neon/vld3_u8
- armintr/_arm_usub16
- arm_neon/vmlsq_lane_s16
- arm_neon/vmovq_n_s8
- arm_neon/int32x4x2_t
- arm_neon/vld4q_u8
- arm_neon/poly16x8x2_t
- arm_neon/vld1q_u64
- arm_neon/vld3q_lane_s16
- arm_neon/int64x1x2_t
- arm_neon/vshlq_n_s8
- arm_neon/vrshl_s64
- arm_neon/vqshl_n_u8
- armintr/_arm_qadd
- armintr/_DSubSatInt
- armintr/_arm_usat16
- arm_neon/vmull_s8
- arm_neon/vsub_s8
- arm_neon/vmovq_n_u16
- arm_neon/vst4_u16
- arm_neon/vmlsl_lane_u32
- arm_neon/vsliq_n_p16
- arm_neon/vmovn_u32
- arm_neon/vbic_u16
- arm_neon/vtbx2_p8
- arm_neon/vrsubhn_s32
- armintr/_SubSatInt
- arm_neon/vst3_u8
- arm_neon/vdupq_n_s32
- arm_neon/vcntq_p8
- arm_neon/vst4_f32
- arm_neon/vbic_s64
- arm_neon/vld3_s64
- arm_neon/vrsra_n_s64
- arm_neon/vqabsq_s16
- arm_neon/vsriq_n_p8
- arm_neon/vst2_lane_p16
- arm_neon/vabsq_s16
- arm_neon/vcombine_u8
- arm_neon/vld2q_p16
- armintr/_CountOneBits
- armintr/__prefetch
- arm_neon/vld3_dup_u64
- arm_neon/vld2q_s16
- arm_neon/vget_low_p16
- arm_neon/vuzpq_u8
- arm_neon/vrev32q_s16
- armintr/_AddSatInt
- arm_neon/uint16x4x2_t
- arm_neon/vmov_n_s32
- arm_neon/vaddl_u16
- arm_neon/vqaddq_s64
- arm_neon/vmlaq_u16
- arm_neon/vsli_n_s8
- armintr/_arm_sxth
- arm_neon/vorr_s32
- arm_neon/vsra_n_u64
- arm_neon/vst2_f16
- arm_neon/vcombine_u16
- arm_neon/vabs_s16
- arm_neon/vsubhn_s32
- arm_neon/vst1q_lane_u32
- arm_neon/vst3_p8
- arm_neon/vqshrun_n_s32
- arm_neon/vcreate_s64
- arm_neon/vld4q_lane_s16
- arm_neon/vzipq_u16
- arm_neon/vmin_s32
- armintr/_CopyInt32FromFloat
- arm_neon/vcgtq_u32
- arm_neon/vabdl_s32
- arm_neon/vqshlq_n_u16
- arm_neon/int8x16x4_t
- arm_neon/vqrdmulh_n_s32
- arm_neon/vqaddq_u64
- arm_neon/vhaddq_s8
- arm_neon/vshll_n_s16
- arm_neon/vuzp_u8
- arm_neon/vaddl_u32
- arm_neon/vld4q_s16
- arm_neon/vqmovun_s16
- arm_neon/vld1q_lane_s8
- arm_neon/vld2_lane_u32
- arm_neon/vrshr_n_s8
- arm_neon/vmlaq_s16
- armintr/_CopyFloatFromInt32
- arm_neon/vmul_f32
- arm_neon/vmlaq_n_f32
- arm_neon/vst4_s16
- arm_neon/vld1_dup_s32
- arm_neon/vmul_u16
- arm_neon/vhaddq_s16
- arm_neon/vst1q_lane_f32
- arm_neon/vrhaddq_u16
- arm_neon/vbicq_u32
- arm_neon/vrev32_s8
- arm_neon/vmlaq_s8
- arm_neon/vmin_s16
- arm_neon/vst3_lane_p16
- arm_neon/vst2q_lane_f32
- arm_neon/vld4q_lane_f32
- arm_neon/vget_low_u16
- arm_neon/vqsub_s32
- arm_neon/vtbl1_s8
- arm_neon/vmovn_s64
- arm_neon/vpmax_s8
- arm_neon/int8x16_t
- arm_neon/vpmin_u8
- arm_neon/vdup_lane_p8
- arm_neon/vsetq_lane_u64
- arm_neon/vuzpq_u16
- arm_neon/vcgeq_u16
- arm_neon/uint8x16x2_t
- armintr/_arm_rev16
- armintr/_arm_sxtb
- arm_neon/vsliq_n_u64
- arm_neon/vmovq_n_u8
- arm_neon/vshlq_n_u32
- arm_neon/vcombine_s64
- armintr/_arm_qsax
- arm_neon/vmin_f32
- armintr/_arm_sadd16
- arm_neon/vmlsq_n_s16
- arm_neon/vorr_u64
- arm_neon/vqrshrun_n_s64
- arm_neon/vld2q_lane_s32
- arm_neon/vgetq_lane_p16
- arm_neon/vrev32_s16
- arm_neon/vqshl_u16
- arm_neon/vtrn_s8
- arm_neon/vst1q_lane_s64
- arm_neon/vtbl4_p8
- arm_neon/vst1_p16
- arm_neon/vmvn_u8
- arm_neon/vld2_lane_u8
- arm_neon/vld2q_u16
- arm_neon/vmovl_s8
- arm_neon/vbslq_u64
- arm_neon/vmls_s8
- arm_neon/vld3q_p16
- arm_neon/vtbl3_u8
- arm_neon/vabs_f32
- arm_neon/vsraq_n_s8
- arm_neon/vqadd_s32
- arm_neon/vmulq_n_s16
- arm_neon/vst3q_s8
- arm_neon/vaddhn_s64
- arm_neon/vmul_n_s16
- arm_neon/vtbl1_p8
- arm_neon/uint64x2x3_t
- arm_neon/vmlsq_s32
- arm_neon/vld2q_lane_u32
- arm_neon/vaddq_u8
- arm_neon/vcombine_f16
- arm_neon/vandq_s16
- arm_neon/vst4q_lane_p16
- arm_neon/vsri_n_u8
- arm_neon/vst3_lane_p8
- arm_neon/vst3_lane_s16
- arm_neon/vdup_n_s16
- arm_neon/vbicq_s8
- arm_neon/vdup_lane_u8
- arm_neon/vst4q_lane_s32
- arm_neon/vqrshl_u16
- arm_neon/vrsra_n_u32
- arm_neon/vdupq_lane_p8
- arm_neon/vld3_lane_u8
- arm_neon/vqrdmulh_n_s16
- arm_neon/vpmin_s32
- armintr/__cps
- arm_neon/vshl_u32
- armintr/_arm_uadd16
- arm_neon/vld3_s16
- arm_neon/vcvt_f32_s32
- arm_neon/vshlq_n_u64
- arm_neon/vrev64q_u8
- arm_neon/vextq_u16
- arm_neon/vsubl_s16
- arm_neon/vget_lane_p8
- arm_neon/vabal_s16
- arm_neon/vrecpeq_u32
- arm_neon/vminq_u8
- arm_neon/veor_s16
- arm_neon/vmull_n_u16
- arm_neon/vshl_n_u8
- arm_neon/vrev32q_u8
- arm_neon/vandq_s8
- arm_neon/vrshlq_s16
- arm_neon/vst4q_p16
- arm_neon/vandq_s32
- armintr/_MoveToCoprocessor2
- arm_neon/vqdmlsl_lane_s32
- arm_neon/vld1q_s64
- arm_neon/vmull_n_s16
- arm_neon/vneg_s16
- arm_neon/vqshluq_n_s64
- arm_neon/vst2_lane_s32
- arm_neon/vmvnq_u16
- arm_neon/vshll_n_s32
- arm_neon/vld3_dup_s8
- arm_neon/vtstq_s32
- arm_neon/vmlsl_u32
- arm_neon/vqdmulhq_lane_s16
- arm_neon/vaddl_s32
- armintr/_CountLeadingZeros
- arm_neon/vqrshrn_n_s16
- arm_neon/vmla_lane_u32
- arm_neon/vst1_u8
- arm_neon/vshl_u64
- arm_neon/vshr_n_u8
- arm_neon/vmull_lane_s32
- arm_neon/vmlal_lane_u32
- arm_neon/vsubl_s8
- arm_neon/float32x2x2_t
- armintr/_arm_bfc
- arm_neon/vaddq_s16
- arm_neon/vmlal_lane_s32
- arm_neon/vpadd_u16
- arm_neon/vst2q_lane_u16
- arm_neon/vld4_s8
- arm_neon/vst1q_s8
- arm_neon/vshrq_n_u64
- arm_neon/vsli_n_u16
- arm_neon/vqrdmulh_lane_s32
- arm_neon/vst4_lane_u16
- arm_neon/vabdq_f32
- arm_neon/vld2_lane_f16
- arm_neon/vqsub_u64
- arm_neon/vsub_f32
- arm_neon/vld1q_s16
- arm_neon/vmaxq_s16
- arm_neon/vcombine_u32
- arm_neon/vrsraq_n_u32
- armintr/_arm_smusdx
- arm_neon/vrev16_s8
- arm_neon/vqdmulh_n_s32
- arm_neon/vmul_s32
- arm_neon/vabdq_s32
- arm_neon/veor_u64
- arm_neon/vmlsl_n_s32
- arm_neon/vsub_s16
- arm_neon/vadd_u16
- arm_neon/vsriq_n_u16
- arm_neon/vmla_u32
- arm_neon/vuzpq_s32
- arm_neon/vst4q_s8
- arm_neon/vaddhn_u32
- arm_neon/vmlaq_lane_f32
- arm_neon/vld3_lane_s8
- arm_neon/vsliq_n_u32
- arm_neon/vqrshlq_s8
- arm_neon/vqdmlal_n_s32
- arm_neon/uint8x16x4_t
- arm_neon/vcgtq_u16
- arm_neon/vandq_u32
- arm_neon/vld4q_lane_u32
- arm_neon/vzip_p16
- arm_neon/vget_low_p8
- armintr/_arm_shadd8
- arm_neon/vmovn_s16
- arm_neon/vcge_u8
- arm_neon/vld2q_f32
- arm_neon/vaba_u32
- armintr/__iso_volatile_store8
- arm_neon/vst2q_p16
- arm_neon/vmul_s16
- arm_neon/vand_s16
- arm_neon/vtbx4_p8
- arm_neon/vceq_u8
- arm_neon/vrhaddq_s16
- arm_neon/vgetq_lane_f32
- arm_neon/vqshl_s8
- arm_neon/vbslq_f32
- arm_neon/vrsqrts_f32
- arm_neon/vld2q_s8
- arm_neon/vtbl1_u8
- arm_neon/vtst_u8
- arm_neon/vrev64q_f32
- arm_neon/vcle_s8
- arm_neon/vsetq_lane_p16
- arm_neon/vcreate_p16
- arm_neon/vabal_s32
- armintr/_arm_smlald
- arm_neon/vmla_f32
- arm_neon/vtbx2_s8
- arm_neon/int64x1x3_t
- arm_neon/vclz_s8
- arm_neon/vorr_s16
- arm_neon/vornq_s64
- arm_neon/vst1q_u64
- arm_neon/vdupq_n_s8
- armintr/_arm_sadd8
- arm_neon/vextq_s32
- armintr/_arm_smuadx
- armintr/_arm_qsub
- arm_neon/vadd_f32
- arm_neon/vrshrq_n_s16
- arm_neon/vqsub_s8
- arm_neon/vld3_f32
- arm_neon/vhadd_s8
- arm_neon/vmull_n_u32
- arm_neon/vdup_n_u64
- arm_neon/vsubw_s32
- armintr/_arm_sxtab
- armintr/_arm_uxtb16
- arm_neon/vmvn_s16
- arm_neon/vst1_lane_s16
- arm_neon/vqrdmulhq_n_s32
- arm_neon/vsriq_n_s32
- arm_neon/poly8x16x2_t
- arm_neon/vadd_u8
- arm_neon/vuzpq_p8
- arm_neon/vst2q_p8
- armintr/__wfi
- arm_neon/vget_high_u16
- arm_neon/vqrshl_u64
- arm_neon/vld1_dup_s64
- arm_neon/vqrshrn_n_s32
- arm_neon/vrshr_n_s64
- arm_neon/vst3_s8
- arm_neon/poly16x4x3_t
- arm_neon/vqrdmulh_lane_s16
- arm_neon/vmvnq_u32
- arm_neon/vqsubq_u32
- arm_neon/vmovq_n_p8
- arm_neon/vtrn_s16
- arm_neon/vld2q_u32
- arm_neon/vqsubq_u16
- arm_neon/vrsqrteq_u32
- arm_neon/vadd_u64
- armintr/_arm_usat
- arm_neon/vcvtq_n_u32_f32
- arm_neon/vaddq_s8
- arm_neon/vrsraq_n_u16
- arm_neon/vqabs_s16
- arm_neon/vsra_n_s8
- arm_neon/vsra_n_s16
- arm_neon/vqshlq_n_u8
- arm_neon/vpadal_s8
- arm_neon/vmlal_n_u16
- armintr/_CopyDoubleFromInt64
- arm_neon/vaddw_u8
- arm_neon/vmulq_n_s32
- arm_neon/vqaddq_s32
- arm_neon/vmla_lane_f32
- arm_neon/vmlaq_lane_s32
- arm_neon/vld1q_dup_u64
- arm_neon/uint16x8_t
- arm_neon/vld2_s32
- arm_neon/vcltq_f32
- arm_neon/vst4q_f32
- arm_neon/vsri_n_u16
- arm_neon/vshlq_s32
- arm_neon/vgetq_lane_u32
- arm_neon/vld1q_dup_f16
- arm_neon/vrev64q_s16
- arm_neon/vrshrq_n_u32
- arm_neon/vld2q_s32
- arm_neon/vcgtq_s8
- arm_neon/vsubhn_u64
- arm_neon/vmls_n_s32
- armintr/_arm_smmlar
- arm_neon/vld3_dup_u8
- arm_neon/vld3q_lane_p16
- arm_neon/vld2_dup_s64
- arm_neon/vqabs_s32
- arm_neon/vqaddq_u8
- arm_neon/vminq_u32
- arm_neon/vpaddl_u16
- arm_neon/vaba_s16
- arm_neon/vmul_u32
- arm_neon/vst1_lane_u16
- arm_neon/vcreate_f32
- arm_neon/vcvt_f16_f32
- arm_neon/vset_lane_s32
- arm_neon/vshl_s8
- arm_neon/vcgt_s16
- arm_neon/vtrn_f32
- arm_neon/vget_high_s64
- arm_neon/vld3_dup_p8
- arm_neon/vcreate_u64
- arm_neon/vext_u64
- arm_neon/vld1q_dup_s16
- arm_neon/vget_lane_s16
- arm_neon/vqdmlal_s16
- arm_neon/vld2_p16
- arm_neon/vld4_u16
- armintr/_arm_smlalbb
- arm_neon/vrev64_u8
- arm_neon/vbslq_s64
- arm_neon/vsubw_u16
- arm_neon/vrsubhn_u32
- arm_neon/vabdq_u8
- arm_neon/vmls_n_u32
- arm_neon/vshr_n_s32
- arm_neon/vmulq_n_u32
- arm_neon/vst3_p16
- arm_neon/vrev32_u16
- arm_neon/int8x8x3_t
- arm_neon/vst2q_lane_u32
- arm_neon/vextq_p16
- arm_neon/vtrnq_f32
- armintr/_arm_smultt
- arm_neon/vqneg_s8
- arm_neon/vmlsq_lane_s32
- arm_neon/vmov_n_p16
- arm_neon/vraddhn_u64
- arm_neon/vrhadd_u32
- arm_neon/vrev64_u32
- arm_neon/vrshrn_n_s32
- arm_neon/vld4q_f32
- arm_neon/vst2_s8
- arm_neon/vrsqrteq_f32
- arm_neon/uint16x4_t
- arm_neon/vget_low_s8
- arm_neon/vst2_lane_u32
- arm_neon/vhsub_s32
- arm_neon/vqdmull_lane_s32
- armintr/_arm_smulwb
- arm_neon/vmlsl_u8
- arm_neon/vdup_lane_s16
- arm_neon/vtbx4_s8
- arm_neon/vld4q_lane_u16
- arm_neon/vget_high_u8
- arm_neon/vclzq_s32
- arm_neon/vld1q_dup_f32
- arm_neon/vtrn_u8
- arm_neon/vqabsq_s8
- arm_neon/vdup_lane_f32
- arm_neon/vqrdmulh_s16
- arm_neon/vst4_u32
- arm_neon/vdup_lane_u32
- arm_neon/vst4_u8
- arm_neon/vmovq_n_s32
- arm_neon/vld2_lane_s8
- arm_neon/vld3_u32
- arm_neon/vsubl_u16
- arm_neon/vqshlu_n_s8
- arm_neon/float32x4_t
- arm_neon/vqshl_n_s32
- arm_neon/float32x2x3_t
- armintr/__hvc
- arm_neon/vst1q_lane_f16
- arm_neon/vmvnq_s16
- arm_neon/vst3q_lane_f32
- arm_neon/vld1q_dup_u8
- arm_neon/vmlsq_s16
- arm_neon/vget_lane_u8
- arm_neon/vld1_lane_s32
- arm_neon/vst4q_s16
- armintr/_arm_qsub8
- arm_neon/vorrq_s32
- arm_neon/vsriq_n_s8
- arm_neon/vqshrn_n_u64
- arm_neon/vdup_n_s32
- armintr/_arm_uhsub8
- arm_neon/vld3_lane_s32
- arm_neon/vbsl_s64
- arm_neon/vld1_dup_f16
- arm_neon/vsli_n_u64
- arm_neon/vraddhn_u32
- arm_neon/vsub_u16
- arm_neon/vcltq_u32
- arm_neon/vminq_f32
- arm_neon/vshl_n_s64
- arm_neon/vld4_u32
- arm_neon/vld1_u32
- arm_neon/vaddhn_u16
- arm_neon/vcvtq_n_f32_s32
- arm_neon/vorn_u64
- arm_neon/vsubhn_u16
- arm_neon/int64x1_t
- arm_neon/vst1q_lane_s8
- arm_neon/vld1q_dup_s32
- arm_neon/vrev32_p8
- arm_neon/vst3q_lane_p16
- arm_neon/vrecpeq_f32
- arm_neon/int8x8x4_t
- arm_neon/vshr_n_u32
- arm_neon/vdupq_lane_s64
- arm_neon/vpaddlq_s8
- arm_neon/vqshl_n_u32
- arm_neon/vmul_u8
- arm_neon/vtbx2_u8
- arm_neon/vshr_n_u64
- arm_neon/vqrshlq_s16
- arm_neon/vst3_lane_u16
- arm_neon/vqsub_u8
- arm_neon/vrsra_n_s16
- arm_neon/vaba_s32
- arm_neon/vsri_n_u64
- arm_neon/vst3q_lane_u32
- arm_neon/vmlsq_n_u32
- arm_neon/poly8x16_t
- arm_neon/vld2_u8
- armintr/_arm_smmulr
- arm_neon/vtst_s16
- armintr/_arm_smmls
- arm_neon/vqdmulh_s16
- arm_neon/vtrnq_u8
- arm_neon/vset_lane_p8
- arm_neon/vmlsl_u16
- arm_neon/vshrn_n_u16
- arm_neon/vld1_dup_p8
- arm_neon/vrev16q_s8
- arm_neon/vmov_n_s8
- arm_neon/vld1_u64
- arm_neon/vpmin_f32
- arm_neon/vmla_n_u16
- arm_neon/vst1_f16
- arm_neon/vqdmlsl_s16
- arm_neon/vmin_u32
- armintr/_arm_qsub16
- arm_neon/vcage_f32
- arm_neon/vornq_u32
- arm_neon/vpadd_s16
- arm_neon/vld1_u8
- arm_neon/vhsubq_s16
- arm_neon/vld1_dup_u32
- arm_neon/vld4_u64
- armintr/_MulHigh
- arm_neon/vmaxq_u8
- arm_neon/vget_lane_u16
- arm_neon/vld2q_u8
- arm_neon/vld1q_dup_p16
- arm_neon/vsraq_n_u8
- arm_neon/vqdmlsl_n_s32
- arm_neon/vst1_s16
- arm_neon/vst1q_s32
- arm_neon/vmaxq_f32
- arm_neon/vqdmulh_lane_s16
- armintr/__isb
- arm_neon/vuzpq_p16
- arm_neon/vmls_lane_s16
- arm_neon/vtbl4_s8
- arm_neon/vst1_lane_p8
- arm_neon/vsubw_s8
- arm_neon/vmin_u8
- arm_neon/vzip_u16
- arm_neon/vld4q_u16
- arm_neon/vshrn_n_s32
- arm_neon/vpadal_u16
- arm_neon/vorrq_s8
- arm_neon/vrshlq_u64
- arm_neon/vst3_lane_s32
- arm_neon/vqshluq_n_s32
- armintr/_arm_shsub16
- arm_neon/vst1_u32
- arm_neon/vrhadd_s16
- arm_neon/vzipq_s32
- arm_neon/vshrq_n_u16
- arm_neon/vcls_s32
- arm_neon/vceq_s8
- arm_neon/vld2q_lane_f16
- arm_neon/vst4q_u8
- arm_neon/vraddhn_u16
- arm_neon/vget_lane_u64
- armintr/_arm_smlsld
- arm_neon/vld3_u64
- arm_neon/vld1_lane_s16
- arm_neon/vabd_f32
- arm_neon/vdupq_n_u16
- armintr/__iso_volatile_store64
- arm_neon/vqsubq_u8
- arm_neon/poly16x8x3_t
- arm_neon/vcltq_s32
- arm_neon/vqnegq_s16
- arm_neon/vqsub_u16
- arm_neon/vaddq_s32
- arm_neon/vqshl_n_s64
- arm_neon/vabdl_s8
- arm_neon/vclsq_s16
- arm_neon/vpaddl_u8
- arm_neon/vmlsq_n_u16
- armintr/_arm_uqadd8
- arm_neon/vhsub_u32
- arm_neon/vset_lane_s16
- arm_neon/vsubl_u32
- arm_neon/vld3_lane_f32
- arm_neon/vcle_s16
- arm_neon/vmovl_u32
- arm_neon/vst3_lane_f16
- arm_neon/vcaltq_f32
- arm_neon/vsubq_s32
- arm_neon/vand_s64
- arm_neon/vst2_u8
- arm_neon/vcombine_p8
- arm_neon/vqdmlal_s32
- arm_neon/vsub_s32
- armintr/_arm_uxtab16
- arm_neon/vmlsq_n_f32
- armintr/_arm_qdsub
- arm_neon/vhaddq_u32
- arm_neon/vhsubq_u16
- arm_neon/vmlsq_lane_u16
- arm_neon/vst4_s64
- armintr/_CountLeadingOnes
- armintr/_arm_smlabt
- arm_neon/vcombine_s32
- arm_neon/vld4_lane_f16
- arm_neon/vadd_s64
- arm_neon/vorrq_u32
- armintr/__sev
- arm_neon/vdupq_lane_s32
- arm_neon/vrecpsq_f32
- arm_neon/vbicq_u16
- arm_neon/vld1_lane_p16
- arm_neon/vrshr_n_u32
- arm_neon/vcgeq_s32
- arm_neon/vld4_dup_s16
- arm_neon/vld1q_p8
- arm_neon/vrshlq_u16
- arm_neon/vmlaq_lane_u32
- arm_neon/vsub_s64
- arm_neon/vcreate_u16
- arm_neon/vget_lane_s32
- arm_neon/vuzp_f32
- arm_neon/vld2_lane_p8
- arm_neon/vuzp_u16
- arm_neon/vorrq_s16
- armintr/_arm_smlaltb
- arm_neon/vrshrn_n_s16
- arm_neon/vabd_s8
- arm_neon/vnegq_s8
- arm_neon/vst4q_u16
- arm_neon/vst1q_lane_s32
- arm_neon/vst1_lane_s32
- arm_neon/vmla_u16
- arm_neon/vmls_lane_s32
- arm_neon/vtst_s8
- arm_neon/vcgeq_s8
- arm_neon/poly8x8x4_t
- arm_neon/vqsub_s64
- armintr/_arm_uqasx
- arm_neon/vld1_lane_u64
- arm_neon/vminq_s16
- arm_neon/vmulq_u32
- arm_neon/vqrshlq_u8
- arm_neon/vdupq_n_p16
- arm_neon/vld4_dup_f16
- arm_neon/vcls_s16
- arm_neon/vmov_n_u64
- arm_neon/vmla_s32
- arm_neon/vrshl_s16
- arm_neon/vcalt_f32
- arm_neon/int64x2x3_t
- arm_neon/vsub_u8
- arm_neon/vzipq_u8
- arm_neon/vrshrn_n_u64
- arm_neon/vrshlq_s32
- arm_neon/vorr_s64
- arm_neon/vqrshl_s16
- arm_neon/vceqq_u16
- arm_neon/vmulq_n_u16
- arm_neon/vmlaq_u8
- arm_neon/vsri_n_s64
- arm_neon/vld3q_u8
- arm_neon/vld1_dup_s16
- arm_neon/vld1q_s32
- arm_neon/vsri_n_s16
- arm_neon/vshlq_u8
- arm_neon/vsli_n_s64
- arm_neon/vmull_lane_u32
- arm_neon/vshl_s64
- arm_neon/vcreate_s16
- arm_neon/uint8x8x4_t
- arm_neon/vqshrn_n_s32
- arm_neon/vqshlq_u32
- arm_neon/vmlal_n_u32
- arm_neon/vtrnq_s16
- arm_neon/vshr_n_s64
- arm_neon/vst2_u16
- arm_neon/vtrn_s32
- arm_neon/vsubhn_u32
- arm_neon/vbicq_s16
- arm_neon/vsetq_lane_s8
- arm_neon/vrsubhn_s16
- arm_neon/vhsub_u8
- arm_neon/vcleq_s32
- arm_neon/vld4_dup_s8
- arm_neon/vmull_u32
- arm_neon/vrshr_n_s16
- arm_neon/vst1q_lane_s16
- arm_neon/vmlsq_lane_u32
- arm_neon/vnegq_f32
- arm_neon/vmin_s8
- arm_neon/vrev16_p8
- arm_neon/vbic_u8
- arm_neon/vclzq_u16
- arm_neon/vcge_u32
- arm_neon/vget_high_u64
- arm_neon/vabsq_s8
- arm_neon/vhaddq_u16
- arm_neon/vsraq_n_s64
- arm_neon/vld2_u32
- arm_neon/vld2_lane_f32
- arm_neon/vqrshrn_n_u32
- arm_neon/vbslq_s8
- armintr/_CountLeadingZeros64
- arm_neon/vbicq_u8
- arm_neon/vdup_lane_s8
- arm_neon/vpadd_s32
- arm_neon/vld3q_lane_f16
- arm_neon/vaba_u8
- arm_neon/vqshlq_u16
- arm_neon/vst1q_u8
- arm_neon/vst4q_lane_f16
- arm_neon/vshl_n_u16
- armintr/_arm_smladx
- arm_neon/vmla_lane_s16
- arm_neon/vornq_u8
- arm_neon/vqneg_s32
- arm_neon/vadd_s8
- arm_neon/vcle_u32
- arm_neon/vclzq_u8
- arm_neon/vtbx1_u8
- armintr/_CountLeadingOnes64
- armintr/__dsb
- arm_neon/vaddq_u32
- arm_neon/vclsq_s8
- arm_neon/vdup_n_s64
- arm_neon/vmax_s16
- arm_neon/vst2q_u32
- arm_neon/vsetq_lane_s64
- arm_neon/vtst_p8
- arm_neon/vabs_s8
- arm_neon/vqshl_n_s16
- arm_neon/vqrshrn_n_u64
- arm_neon/vaddw_s8
- armintr/_arm_uhadd16
- arm_neon/vsriq_n_p16
- arm_neon/vld4_lane_u32
- arm_neon/vneg_f32
- armintr/_MoveToCoprocessor
- arm_neon/vmvnq_s8
- arm_neon/vld1q_lane_p8
- arm_neon/uint32x2x3_t
- arm_neon/vrshrn_n_u16
- arm_neon/vld3_f16
- arm_neon/vsriq_n_s16
- arm_neon/vshlq_n_s16
- arm_neon/vabal_u8
- arm_neon/vqshluq_n_s16
- arm_neon/vst2_lane_u16
- arm_neon/vbic_s16
- arm_neon/vqshl_n_u64
- arm_neon/vcagt_f32
- arm_neon/vpadalq_s8
- arm_neon/vclz_s32
- arm_neon/vld1_lane_s64
- arm_neon/vget_high_p8
- arm_neon/uint64x1_t
- arm_neon/vextq_s16
- arm_neon/vpadd_s8
- arm_neon/vrsubhn_u64
- arm_neon/vst3q_f16
- arm_neon/vdupq_lane_u16
- arm_neon/vrshrq_n_u64
- arm_neon/vmovq_n_f32
- arm_neon/vld1q_dup_u16
- arm_neon/vshr_n_u16
- arm_neon/uint32x2_t
- armintr/_arm_umull
- arm_neon/vtrnq_u16
- arm_neon/vsetq_lane_u32
- arm_neon/vneg_s8
- arm_neon/vsetq_lane_u8
- arm_neon/vst2q_lane_s16
- arm_neon/vqmovun_s32
- armintr/_arm_usad8
- armintr/_arm_pkhbt
- arm_neon/uint16x4x3_t
- arm_neon/vsra_n_s32
- arm_neon/vqmovun_s64
- arm_neon/vld1q_dup_s8
- arm_neon/vaddhn_s32
- arm_neon/vpmax_f32
- arm_neon/vpadd_u32
- arm_neon/vhsubq_u32
- arm_neon/vqrshrun_n_s32
- arm_neon/vadd_s32
- arm_neon/vclt_s8
- arm_neon/vorrq_s64
- arm_neon/vst4q_f16
- arm_neon/vst1_s32
- arm_neon/vceq_p8
- arm_neon/vsubw_s16
- arm_neon/vgetq_lane_u64
- arm_neon/vmla_n_u32
- arm_neon/vcvtq_f32_s32
- arm_neon/vld1q_u32
- arm_neon/vmax_f32
- armintr/_isunorderedf
- arm_neon/vrshl_u8
- arm_neon/vld4_dup_s64
- arm_neon/vqaddq_u16
- arm_neon/vld4q_lane_f16
- arm_neon/vceqq_p8
- arm_neon/vsubw_u8
- arm_neon/vqmovn_u16
- armintr/_arm_smlsldx
- arm_neon/vcreate_p8
- arm_neon/vqdmull_n_s32
- arm_neon/uint64x2_t
- arm_neon/vmls_s32
- arm_neon/vst3q_f32
- armintr/_arm_bfi
- armintr/_arm_qadd16
- arm_neon/vrshlq_s8
- arm_neon/vget_lane_p16
- arm_neon/vld2_p8
- arm_neon/vld3_lane_u32
- armintr/_MoveFromCoprocessor2
- arm_neon/vqshl_u8
- arm_neon/poly8_t
- arm_neon/vhadd_u16
- arm_neon/vmla_lane_u16
- arm_neon/vshrq_n_u8
- arm_neon/vuzpq_f32
- arm_neon/vmls_lane_f32
- arm_neon/vqneg_s16
- arm_neon/vtrn_p16
- arm_neon/vshrn_n_u32
- arm_neon/vaddhn_u64
- arm_neon/vabal_u32
- arm_neon/vld1q_lane_u32
- arm_neon/vrsraq_n_s32
- arm_neon/vandq_u64
- arm_neon/vqdmull_s32
- arm_neon/vext_s16
- arm_neon/vaddw_s16
- arm_neon/vrev64q_p8
- arm_neon/uint8x8x3_t
- arm_neon/vzip_f32
- armintr/_arm_ssub8
- arm_neon/uint16x4x4_t
- armintr/__swi
- armintr/_arm_smlatb
- arm_neon/vrhaddq_s8
- arm_neon/vpmax_s32
- arm_neon/vqshl_s64
- arm_neon/vrev16q_p8
- arm_neon/vqmovn_u32
- arm_neon/vld1q_f16
- arm_neon/vornq_u64
- arm_neon/vqshlq_n_s16
- arm_neon/vld1_f16
- armintr/_arm_smmlsr
- arm_neon/vshlq_s16
- arm_neon/vsubhn_s16
- arm_neon/vmulq_p8
- arm_neon/vdupq_lane_f32
- armintr/_arm_shadd16
- arm_neon/vornq_s16
- arm_neon/vst1q_lane_u8
- arm_neon/vcaleq_f32
- arm_neon/vst3q_lane_f16
- armintr/_arm_sdiv
- arm_neon/vld2_u16
- arm_neon/vdup_lane_u16
- arm_neon/vst4q_lane_f32
- arm_neon/vdup_n_f32
- arm_neon/vsubq_u8
- arm_neon/vset_lane_p16
- arm_neon/vrsqrte_f32
- arm_neon/vsubl_u8
- arm_neon/vld3q_lane_f32
- arm_neon/vqnegq_s8
- arm_neon/vqmovn_s16
- arm_neon/int16x8x3_t
- arm_neon/veorq_u16
- arm_neon/vqdmulh_n_s16
- arm_neon/vhaddq_u8
- arm_neon/vpadal_u8
- arm_neon/vst2q_s16
- arm_neon/poly16x8x4_t
- arm_neon/int64x2_t
- arm_neon/vmull_s32
- arm_neon/vld4_lane_s32
- arm_neon/vst4q_p8
- arm_neon/vmlal_lane_u16
- arm_neon/vclz_u32
- arm_neon/vsliq_n_s8
- arm_neon/vmls_n_f32
- arm_neon/vmlsl_lane_s16
- arm_neon/vst4q_u32
- arm_neon/vld1q_lane_s16
- arm_neon/vst1q_f32
- arm_neon/vrshr_n_u8
- arm_neon/vst1q_s64
- arm_neon/vbslq_u32
- arm_neon/vset_lane_s8
- arm_neon/vdupq_lane_p16
- arm_neon/vtstq_s16
- arm_neon/vshl_n_s8
- arm_neon/vqrdmulhq_n_s16
- arm_neon/vget_high_f16
- arm_neon/vst4_lane_u32
- arm_neon/vraddhn_s16
- arm_neon/vmlsl_lane_s32
- arm_neon/vld3q_s32
- arm_neon/vsriq_n_u64
- arm_neon/vld4_dup_u8
- arm_neon/vld4q_s8
- arm_neon/vqmovn_s64
- arm_neon/vrev32q_p8
- arm_neon/vsliq_n_p8
- arm_neon/vzipq_s16
- arm_neon/vgetq_lane_s64
- arm_neon/vst4_p16
- arm_neon/vsubq_u16
- arm_neon/vrev64_s32
- armintr/_arm_uhadd8
- arm_neon/vornq_u16
- arm_neon/vst4_lane_s8
- arm_neon/vabd_s32
- arm_neon/vqrdmulhq_s16
- arm_neon/vqshlq_s32
- arm_neon/int64x2x4_t
- arm_neon/vset_lane_u16
- arm_neon/vrsra_n_s32
- arm_neon/vabdl_u16
- arm_neon/vsliq_n_s32
dev_langs: C++
helpviewer_keywords:
- cl.exe compiler, intrinsics
- intrinsics, ARM
ms.assetid: d3d7dadd-7bd5-4508-8bff-371a66913e20
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 10de33fd0baf8ffb5ccce5fc5a532413f27a2b42
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="arm-intrinsics"></a>ARM İç Bilgileri
Visual C++ derleyicisi aşağıdaki ön tanımlı ARM mimarisine kullanılabilir hale getirir. ARM hakkında daha fazla bilgi için bkz: [ARM mimarisi başvuru kılavuzlarına](http://go.microsoft.com/fwlink/p/?LinkId=522049) ve [ARM Assembler araçları Kılavuzu](http://go.microsoft.com/fwlink/p/?LinkId=246102) ARM Bilgi Merkezi Web sitesinde.  
  
##  <a name="top"></a>NEON  
 ARM NEON vektör yönerge kümesi uzantıları x86 hem x64 mimarisi işlemcileri için ortak olan MMX ve SSE vektör yönerge kümeleri de benzer tek yönerge birden çok veri (SIMD) özellikleri sağlar.  
  
 NEON iç bilgileri desteklenir, üstbilgi dosyasında koşuluyla `arm_neon.h`. Visual C++ Derleyici desteği NEON iç bilgileri için ek G belgelenen ARM derleyici benzer [ARM derleyici araç zinciri, sürümü 4.1 derleyici başvurusu](http://go.microsoft.com/fwlink/p/?LinkId=251083) ARM Bilgi Merkezi Web sitesinde.  
  
 Visual C++ derleyicisi eklediği Visual C++ derleyicisi ve ARM derleyici arasındaki birincil fark olan `_ex` çeşitlemelerini `vldX` ve `vstX` vektör yük ve yönergeleri saklayın. `_ex` Çeşitleri ele işaretçi değişkeni ancak özdeş kendi olmayan aksi hizalamasını belirtir ek bir parametre`_ex` ortaklarınıza.  
  
##  <a name="A"></a>ARM özgü iç bilgi listesi  
  
|İşlev adı|Yönergesi|İşlev prototipi|  
|-------------------|-----------------|------------------------|  
|_arm_smlal|SMLAL|__int64 _arm_smlal (\__int64 _RdHiLo, int _Rn int _Rm)|  
|_arm_umlal|UMLAL|İmzasız __int64 _arm_umlal (imzasız \__int64 _RdHiLo, imzasız int _Rn int _Rm imzasız)|  
|_arm_clz|CLZ|İmzasız int _arm_clz (imzasız int _Rm)|  
|_arm_qadd|QADD|int _arm_qadd (int _Rm, int _Rn)|  
|_arm_qdadd|QDADD|int _arm_qdadd (int _Rm, int _Rn)|  
|_arm_qdsub|QDSUB|int _arm_qdsub (int _Rm, int _Rn)|  
|_arm_qsub|QSUB|int _arm_qsub (int _Rm, int _Rn)|  
|_arm_smlabb|SMLABB|int _arm_smlabb (int _Rn, int _Rm, int _Ra)|  
|_arm_smlabt|SMLABT|int _arm_smlabt (int _Rn, int _Rm, int _Ra)|  
|_arm_smlatb|SMLATB|int _arm_smlatb (int _Rn, int _Rm, int _Ra)|  
|_arm_smlatt|SMLATT|int _arm_smlatt (int _Rn, int _Rm, int _Ra)|  
|_arm_smlalbb|SMLALBB|__int64 _arm_smlalbb (\__int64 _RdHiLo, int _Rn int _Rm)|  
|_arm_smlalbt|SMLALBT|__int64 _arm_smlalbt (\__int64 _RdHiLo, int _Rn int _Rm)|  
|_arm_smlaltb|SMLALTB|__int64 _arm_smlaltb (\__int64 _RdHiLo, int _Rn int _Rm)|  
|_arm_smlaltt|SMLALTT|__int64 _arm_smlaltt (\__int64 _RdHiLo, int _Rn int _Rm)|  
|_arm_smlawb|SMLAWB|int _arm_smlawb (int _Rn, int _Rm, int _Ra)|  
|_arm_smlawt|SMLAWT|int _arm_smlawt (int _Rn, int _Rm, int _Ra)|  
|_arm_smulbb|SMULBB|int _arm_smulbb (int _Rn, int _Rm)|  
|_arm_smulbt|SMULBT|int _arm_smulbt (int _Rn, int _Rm)|  
|_arm_smultb|SMULTB|int _arm_smultb (int _Rn, int _Rm)|  
|_arm_smultt|SMULTT|int _arm_smultt (int _Rn, int _Rm)|  
|_arm_smulwb|SMULWB|int _arm_smulwb (int _Rn, int _Rm)|  
|_arm_smulwt|SMULWT|int _arm_smulwt (int _Rn, int _Rm)|  
|_arm_sadd16|SADD16|int _arm_sadd16 (int _Rn, int _Rm)|  
|_arm_sadd8|SADD8|int _arm_sadd8 (int _Rn, int _Rm)|  
|_arm_sasx|SASX|int _arm_sasx (int _Rn, int _Rm)|  
|_arm_ssax|SSAX|int _arm_ssax (int _Rn, int _Rm)|  
|_arm_ssub16|SSUB16|int _arm_ssub16 (int _Rn, int _Rm)|  
|_arm_ssub8|SSUB8|int _arm_ssub8 (int _Rn, int _Rm)|  
|_arm_shadd16|SHADD16|int _arm_shadd16 (int _Rn, int _Rm)|  
|_arm_shadd8|SHADD8|int _arm_shadd8 (int _Rn, int _Rm)|  
|_arm_shasx|SHASX|int _arm_shasx (int _Rn, int _Rm)|  
|_arm_shsax|SHSAX|int _arm_shsax (int _Rn, int _Rm)|  
|_arm_shsub16|SHSUB16|int _arm_shsub16 (int _Rn, int _Rm)|  
|_arm_shsub8|SHSUB8|int _arm_shsub8 (int _Rn, int _Rm)|  
|_arm_qadd16|QADD16|int _arm_qadd16 (int _Rn, int _Rm)|  
|_arm_qadd8|QADD8|int _arm_qadd8 (int _Rn, int _Rm)|  
|_arm_qasx|QASX|int _arm_qasx (int _Rn, int _Rm)|  
|_arm_qsax|QSAX|int _arm_qsax (int _Rn, int _Rm)|  
|_arm_qsub16|QSUB16|int _arm_qsub16 (int _Rn, int _Rm)|  
|_arm_qsub8|QSUB8|int _arm_qsub8 (int _Rn, int _Rm)|  
|_arm_uadd16|UADD16|İmzasız int _arm_uadd16 (imzasız int _Rn, imzasız int _Rm)|  
|_arm_uadd8|UADD8|İmzasız int _arm_uadd8 (imzasız int _Rn, imzasız int _Rm)|  
|_arm_uasx|UASX|İmzasız int _arm_uasx (imzasız int _Rn, imzasız int _Rm)|  
|_arm_usax|USAX|İmzasız int _arm_usax (imzasız int _Rn, imzasız int _Rm)|  
|_arm_usub16|USUB16|İmzasız int _arm_usub16 (imzasız int _Rn, imzasız int _Rm)|  
|_arm_usub8|USUB8|İmzasız int _arm_usub8 (imzasız int _Rn, imzasız int _Rm)|  
|_arm_uhadd16|UHADD16|İmzasız int _arm_uhadd16 (imzasız int _Rn, imzasız int _Rm)|  
|_arm_uhadd8|UHADD8|İmzasız int _arm_uhadd8 (imzasız int _Rn, imzasız int _Rm)|  
|_arm_uhasx|UHASX|İmzasız int _arm_uhasx (imzasız int _Rn, imzasız int _Rm)|  
|_arm_uhsax|UHSAX|İmzasız int _arm_uhsax (imzasız int _Rn, imzasız int _Rm)|  
|_arm_uhsub16|UHSUB16|İmzasız int _arm_uhsub16 (imzasız int _Rn, imzasız int _Rm)|  
|_arm_uhsub8|UHSUB8|İmzasız int _arm_uhsub8 (imzasız int _Rn, imzasız int _Rm)|  
|_arm_uqadd16|UQADD16|İmzasız int _arm_uqadd16 (imzasız int _Rn, imzasız int _Rm)|  
|_arm_uqadd8|UQADD8|İmzasız int _arm_uqadd8 (imzasız int _Rn, imzasız int _Rm)|  
|_arm_uqasx|UQASX|İmzasız int _arm_uqasx (imzasız int _Rn, imzasız int _Rm)|  
|_arm_uqsax|UQSAX|İmzasız int _arm_uqsax (imzasız int _Rn, imzasız int _Rm)|  
|_arm_uqsub16|UQSUB16|İmzasız int _arm_uqsub16 (imzasız int _Rn, imzasız int _Rm)|  
|_arm_uqsub8|UQSUB8|İmzasız int _arm_uqsub8 (imzasız int _Rn, imzasız int _Rm)|  
|_arm_sxtab|SXTAB|int _arm_sxtab (int _Rn, int _Rm, imzasız int _Rotation)|  
|_arm_sxtab16|SXTAB16|int _arm_sxtab16 (int _Rn, int _Rm imzalanmamış int _Rotation)|  
|_arm_sxtah|SXTAH|int _arm_sxtah (int _Rn, int _Rm, imzasız int _Rotation)|  
|_arm_uxtab|UXTAB|İmzasız int _arm_uxtab (imzasız int _Rn, imzasız int _Rm, imzasız int _Rotation)|  
|_arm_uxtab16|UXTAB16|İmzasız int _arm_uxta16b (int _Rn, imzasız int _Rm, imzasız int _Rotation imzasız)|  
|_arm_uxtah|UXTAH|İmzasız int _arm_uxtah (imzasız int _Rn, imzasız int _Rm, imzasız int _Rotation)|  
|_arm_sxtb|SXTB|int _arm_sxtb (int _Rn, imzasız int _Rotation)|  
|_arm_sxtb16|SXTB16|int _arm_sxtb16 (int _Rn, imzasız int _Rotation)|  
|_arm_sxth|SXTH|int _arm_sxth (int _Rn, imzasız int _Rotation)|  
|_arm_uxtb|UXTB|İmzasız int _arm_uxtb (imzasız int _Rn, imzasız int _Rotation)|  
|_arm_uxtb16|UXTB16|İmzasız int _arm_uxtb16 (imzasız int _Rn, imzasız int _Rotation)|  
|_arm_uxth|UXTH|İmzasız int _arm_uxth (imzasız int _Rn, imzasız int _Rotation)|  
|_arm_pkhbt|PKHBT|int _arm_pkhbt (int _Rn, int _Rm, imzasız int _Lsl_imm)|  
|_arm_pkhtb|PKHTB|int _arm_pkhtb (int _Rn, int _Rm, imzasız int _Asr_imm)|  
|_arm_usad8|USAD8|İmzasız int _arm_usad8 (imzasız int _Rn, imzasız int _Rm)|  
|_arm_usada8|USADA8|İmzasız int _arm_usada8 (int _Rn, imzasız int _Rm, imzasız int _Ra imzasız)|  
|_arm_ssat|SSAT|int _arm_ssat (imzasız int _Sat_imm, _int _Rn, _ARMINTR_SHIFT_T _Shift_type, imzasız int _Shift_imm)|  
|_arm_usat|USAT|int _arm_usat (imzasız int _Sat_imm, _int _Rn, _ARMINTR_SHIFT_T _Shift_type, imzasız int _Shift_imm)|  
|_arm_ssat16|SSAT16|int _arm_ssat16 (imzasız int _Sat_imm, _int _Rn)|  
|_arm_usat16|USAT16|int _arm_usat16 (imzasız int _Sat_imm, _int _Rn)|  
|_arm_rev|REV|İmzasız int _arm_rev (imzasız int _Rm)|  
|_arm_rev16|REV16|İmzasız int _arm_rev16 (imzalanmamış int _Rm)|  
|_arm_revsh|REVSH|İmzasız int _arm_revsh (imzasız int _Rm)|  
|_arm_smlad|SMLAD|int _arm_smlad (int _Rn, int _Rm, int _Ra)|  
|_arm_smladx|SMLADX|int _arm_smladx (int _Rn, int _Rm, int _Ra)|  
|_arm_smlsd|SMLSD|int _arm_smlsd (int _Rn, int _Rm, int _Ra)|  
|_arm_smlsdx|SMLSDX|int _arm_smlsdx (int _Rn, int _Rm, int _Ra)|  
|_arm_smmla|SMMLA|int _arm_smmla (int _Rn, int _Rm, int _Ra)|  
|_arm_smmlar|SMMLAR|int _arm_smmlar (int _Rn, int _Rm, int _Ra)|  
|_arm_smmls|SMMLS|int _arm_smmls (int _Rn, int _Rm, int _Ra)|  
|_arm_smmlsr|SMMLSR|int _arm_smmlsr (int _Rn, int _Rm, int _Ra)|  
|_arm_smmul|SMMUL|int _arm_smmul (int _Rn, int _Rm)|  
|_arm_smmulr|SMMULR|int _arm_smmulr (int _Rn, int _Rm)|  
|_arm_smlald|SMLALD|__int64 _arm_smlald (\__int64 _RdHiLo, int _Rn int _Rm)|  
|_arm_smlaldx|SMLALDX|__int64 _arm_smlaldx (\__int64 _RdHiLo, int _Rn int _Rm)|  
|_arm_smlsld|SMLSLD|__int64 _arm_smlsld (\__int64 _RdHiLo, int _Rn int _Rm)|  
|_arm_smlsldx|SMLSLDX|__int64 _arm_smlsldx (\__int64 _RdHiLo, int _Rn int _Rm)|  
|_arm_smuad|SMUAD|int _arm_smuad (int _Rn, int _Rm)|  
|_arm_smuadx|SMUADX|int _arm_muadxs (int _Rn, int _Rm)|  
|_arm_smusd|SMUSD|int _arm_smusd (int _Rn, int _Rm)|  
|_arm_smusdx|SMUSDX|int _arm_smusdx (int _Rn, int _Rm)|  
|_arm_smull|SMULL|__int64 _arm_smull (int _Rn, int _Rm)|  
|_arm_umull|UMULL|İmzasız __int64 _arm_umull (imzasız int _Rn, imzasız int _Rm)|  
|_arm_umaal|UMAAL|İmzasız __int64 _arm_umaal (imzasız int _RdLo, imzasız int _RdHi, imzasız int _Rn, imzasız int _Rm)|  
|_arm_bfc|BFC|İmzasız int _arm_bfc (imzasız int _Rd, imzasız int _Lsb, imzasız int _Width)|  
|_arm_bfi|BFI|İmzasız int _arm_bfi (imzasız int _Rd, imzasız int _Rn, imzasız int _Lsb, imzasız int _Width)|  
|_arm_rbit|RBIT|İmzasız int _arm_rbit (imzasız int _Rm)|  
|_arm_sbfx|SBFX|int _arm_sbfx (int _Rn, imzasız int _Lsb, imzasız int _Width)|  
|_arm_ubfx|UBFX|İmzasız int _arm_ubfx (imzasız int _Rn, imzasız int _Lsb, imzasız int _Width)|  
|_arm_sdiv|SDIV|int _arm_sdiv (int _Rn, int _Rm)|  
|_arm_udiv|UDIV|İmzasız int _arm_udiv (imzasız int _Rn, imzasız int _Rm)|  
|__cps|CPS|void __cps (imzasız int _Ops, imzasız int _Flags, imzasız int _Mode)|  
|__dmb|DMB|void __dmb (imzalanmamış int `_Type`)<br /><br /> Bellek engeli işlem yönergesi akışa ekler. Parametre `_Type` engel zorlar kısıtlama türünü belirtir.<br /><br /> Zorunlu tutulabilir kısıtlamaları türleri hakkında daha fazla bilgi için bkz: [bellek engeli kısıtlamaları](#BarrierRestrictions).|  
|__dsb|DSB|void __dsb (imzasız int _ad)<br /><br /> Bellek engeli işlem yönergesi akışa ekler. Parametre `_Type` engel zorlar kısıtlama türünü belirtir.<br /><br /> Zorunlu tutulabilir kısıtlamaları türleri hakkında daha fazla bilgi için bkz: [bellek engeli kısıtlamaları](#BarrierRestrictions).|  
|__isb|ISB|void __isb (imzasız int _ad)<br /><br /> Bellek engeli işlem yönergesi akışa ekler. Parametre `_Type` engel zorlar kısıtlama türünü belirtir.<br /><br /> Zorunlu tutulabilir kısıtlamaları türleri hakkında daha fazla bilgi için bkz: [bellek engeli kısıtlamaları](#BarrierRestrictions).|  
|__emit||void __emit (imzasız \__int32 opcode)<br /><br /> Belirtilen bir yönerge derleyici tarafından çıkış akışı yönerge ekler.<br /><br /> Değerini `opcode` derleme zamanında bilinen sabit bir ifade olması gerekir. 16 bit ve en önemli 16 bit düzeyi bir yönerge word'ün boyutudur `opcode` göz ardı edilir.<br /><br /> Derleyici içeriğini yorumlama girişimi yapar `opcode` ve eklenen yönerge yürütülmeden önce bir CPU veya bellek durumu garanti etmez.<br /><br /> Derleyici eklenen yönerge yürütüldükten sonra CPU ve bellek durumlarını değiştirilmemiş olduğunu varsayar. Bu nedenle, durumunu değiştirme yönergeleri, derleyici tarafından üretilen normal kodu detrimental bir etkisi olabilir.<br /><br /> Bu nedenle, kullanmak `emit` yalnızca derleyici normalde işleyemez CPU durumunu etkileyen yönergeleri eklemek için — örneğin, eşişlemcisi durumu — veya kullanarak bildirilen işlevlerini gerçekleştirmek için `declspec(naked)`.|  
|__hvc|HVC|İmzasız int __hvc (imzasız int,...)|  
|__iso_volatile_load16||__int16 \__iso_volatile_load16 (const geçici \__int16 *)<br /><br /> Daha fazla bilgi için bkz: [__iso_volatile_load/deposu instrinsics](#IsoVolatileLoadStore).|  
|__iso_volatile_load32||__int32 \__iso_volatile_load32 (const geçici \__int32 *)<br /><br /> Daha fazla bilgi için bkz: [__iso_volatile_load/deposu instrinsics](#IsoVolatileLoadStore).|  
|__iso_volatile_load64||__int64 \__iso_volatile_load64 (const geçici \__int64 *)<br /><br /> Daha fazla bilgi için bkz: [__iso_volatile_load/deposu instrinsics](#IsoVolatileLoadStore).|  
|__iso_volatile_load8||__int8 \__iso_volatile_load8 (const geçici \__int8 *)<br /><br /> Daha fazla bilgi için bkz: [__iso_volatile_load/deposu instrinsics](#IsoVolatileLoadStore).|  
|__iso_volatile_store16||void __iso_volatile_store16 (geçici \__int16 *, \__int16)<br /><br /> Daha fazla bilgi için bkz: [__iso_volatile_load/deposu instrinsics](#IsoVolatileLoadStore).|  
|__iso_volatile_store32||void __iso_volatile_store32 (geçici \__int32 *, \__int32)<br /><br /> Daha fazla bilgi için bkz: [__iso_volatile_load/deposu instrinsics](#IsoVolatileLoadStore).|  
|__iso_volatile_store64||void __iso_volatile_store64 (geçici \__int64 *, \__int64)<br /><br /> Daha fazla bilgi için bkz: [__iso_volatile_load/deposu instrinsics](#IsoVolatileLoadStore).|  
|__iso_volatile_store8||void __iso_volatile_store8 (geçici \__int8 *, \__int8)<br /><br /> Daha fazla bilgi için bkz: [__iso_volatile_load/deposu instrinsics](#IsoVolatileLoadStore).|  
|__ldrexd|LDREXD|__int64 \__ldrexd (const geçici \__int64 *)|  
|__prefetch|PLD|void __cdecl \__prefetch(const void *)<br /><br /> Sağlayan bir `PLD` bellek, bellek veya belirtilen yakın sisteme ipucu adresi erişilebilir yakında. Çalışma zamanı performansı artırmak bu bellek erişim düzeni için optimize etmek bazı sistemleri seçebilirsiniz. Ancak, açısından C++ dili, işlevi observable etkisi yoktur ve hiçbir şey hiç yapabilirsiniz.|  
|__rdpmccntr64||İmzasız __int64 \__rdpmccntr64(void)|  
|__sev|ÖNEM DÜZEYİ|void __sev(void)|  
|__static_assert||void __static_assert (int, const char *)|  
|__swi|SVC|İmzasız int __swi (imzasız int,...)|  
|__trap|BKPT|int __trap (int,...)|  
|__wfe|WFE|void __wfe(void)|  
|__wfi|WFI|void __wfi(void)|  
|_AddSatInt|QADD|int _AddSatInt (int, int)|  
|_CopyDoubleFromInt64||çift _CopyDoubleFromInt64 (\__int64)|  
|_CopyFloatFromInt32||_CopyFloatFromInt32 float (\__int32)|  
|_CopyInt32FromFloat||__int32 _CopyInt32FromFloat(float)|  
|_CopyInt64FromDouble||__int64 _CopyInt64FromDouble(double)|  
|_CountLeadingOnes||İmzasız int _CountLeadingOnes(unsigned long)|  
|_CountLeadingOnes64||İmzasız int _CountLeadingOnes64 (imzasız \__int64)|  
|_CountLeadingSigns||İmzasız int _CountLeadingSigns(long)|  
|_CountLeadingSigns64||İmzasız int _CountLeadingSigns64 (\__int64)|  
|_CountLeadingZeros||İmzasız int _CountLeadingZeros(unsigned long)|  
|_CountLeadingZeros64||İmzasız int _CountLeadingZeros64 (imzasız \__int64)|  
|_CountOneBits||İmzasız int _CountOneBits(unsigned long)|  
|_CountOneBits64||İmzasız int _CountOneBits64 (imzasız \__int64)|  
|_DAddSatInt|QDADD|int _DAddSatInt (int, int)|  
|_DSubSatInt|QDSUB|int _DSubSatInt (int, int)|  
|_isunordered||int _isunordered (double, çift)|  
|_isunorderedf||int _isunorderedf (float, float)|  
|_MoveFromCoprocessor|MRC|İmzasız int _MoveFromCoprocessor (imzasız int, imzasız int, imzasız int, imzasız int, imzasız int)<br /><br /> Eşişlemcisi veri aktarımı yönergeleri kullanarak ARM eşişlemcisi verileri okur. Daha fazla bilgi için bkz: [_MoveFromCoprocessor, _MoveFromCoprocessor2](#MoveFromCo).|  
|_MoveFromCoprocessor2|MRC2|İmzasız int _MoveFromCoprocessor2 (int, imzasız int, imzasız int, imzasız int, imzasız int imzasız)<br /><br /> Eşişlemcisi veri aktarımı yönergeleri kullanarak ARM eşişlemcisi verileri okur. Daha fazla bilgi için bkz: [_MoveFromCoprocessor, _MoveFromCoprocessor2](#MoveFromCo).|  
|_MoveFromCoprocessor64|MRRC|İmzasız __int64 _MoveFromCoprocessor64 (int, imzasız int, imzasız int imzasız)<br /><br /> Eşişlemcisi veri aktarımı yönergeleri kullanarak ARM eşişlemcisi verileri okur. Daha fazla bilgi için bkz: [_MoveFromCoprocessor64](#MoveFromCo64).|  
|_MoveToCoprocessor|MCR|void _MoveToCoprocessor (imzasız int, imzasız int, imzasız int, imzasız int, imzasız int, imzasız int)<br /><br /> Eşişlemcisi veri aktarımı yönergeleri kullanarak ARM eşişlemcisi verileri okur. Daha fazla bilgi için bkz: [_MoveToCoprocessor, _MoveToCoprocessor2](#MoveToCo).|  
|_MoveToCoprocessor2|MCR2|void _MoveToCoprocessor2 (int, imzasız int, imzasız int, imzasız int, imzasız int, imzasız int imzasız)<br /><br /> Eşişlemcisi veri aktarımı yönergeleri kullanarak ARM eşişlemcisi verileri okur. Daha fazla bilgi için bkz: [_MoveToCoprocessor, _MoveToCoprocessor2](#MoveToCo).|  
|_MoveToCoprocessor64|MCRR|void _MoveToCoprocessor64 (imzasız \__int64, imzasız int, imzasız int, int imzasız)<br /><br /> Eşişlemcisi veri aktarımı yönergeleri kullanarak ARM eşişlemcisi verileri okur. Daha fazla bilgi için bkz: [_MoveToCoprocessor64](#MoveToCo64).|  
|_MulHigh||_MulHigh uzun (uzun, uzun)|  
|_MulUnsignedHigh||uzun _MulUnsignedHigh (imzasız long, imzasız long) imzalanmamış|  
|_ReadBankedReg|MRS|int _ReadBankedReg (int _Reg)|  
|_ReadStatusReg|MRS|int _ReadStatusReg(int)|  
|_SubSatInt|QSUB|int _SubSatInt (int, int)|  
|_WriteBankedReg|MSR|void _WriteBankedReg (int _Value, int _Reg)|  
|_WriteStatusReg|MSR|void _WriteStatusReg (int, int, int)|  
  
 [[NEON](#top)]  
  
###  <a name="BarrierRestrictions"></a>Bellek engeli kısıtlamaları  
 İç işlevler `__dmb` (veri bellek engeli) `__dsb` (veri eşitleme engel) ve `__isb` (yönerge eşitleme engel) kullanımı bellek engeli kısıtlama koşulları belirtmek için değerleri aşağıdaki önceden tanımlanmış Paylaşım etki alanı ve işlem tarafından etkilenen erişimi türü.  
  
|Kısıtlama değeri|Açıklama|  
|-----------------------|-----------------|  
|_ARM_BARRIER_SY|Tam sistem, okuma ve yazma işlemleri.|  
|_ARM_BARRIER_ST|Tam sistem, yalnızca yazar.|  
|_ARM_BARRIER_ISH|İç paylaşılabilir, okuma ve yazma işlemleri.|  
|_ARM_BARRIER_ISHST|İç paylaşılabilir, yazma işlemleri yalnızca.|  
|_ARM_BARRIER_NSH|Olmayan paylaşılabilir, okuma ve yazma işlemleri.|  
|_ARM_BARRIER_NSHST|Yalnızca olmayan paylaşılabilir, yazar.|  
|_ARM_BARRIER_OSH|Dış paylaşılabilir, okuma ve yazma işlemleri.|  
|_ARM_BARRIER_OSHST|Dış paylaşılabilir, yazma işlemleri yalnızca.|  
  
 İçin `__isb` iç, şu anda geçerli olan tek kısıtlama _ARM_BARRIER_SY; diğer tüm değerler tarafından mimarisi ayrılmıştır.  
  
###  <a name="IsoVolatileLoadStore"></a>__iso_volatile_load/deposu instrinsics  
 Bu iç işlevleri açıkça yükler ve derleyici iyileştirmelerini tabi olmayan depoları gerçekleştirin.  
  
```  
__int16 __iso_volatile_load16(const volatile __int16 * Location)  
__int32 __iso_volatile_load32(const volatile __int32 * Location)  
__int64 __iso_volatile_load64(const volatile __int64 * Location)  
__int8 __iso_volatile_load8(const volatile __int8 * Location)  
  
void __iso_volatile_store16(volatile __int16 * Location, __int16 Value)  
void __iso_volatile_store32(volatile __int32 * Location, __int32 Value)  
void __iso_volatile_store64(volatile __int64 * Location, __int64 Value)  
void __iso_volatile_store8(volatile __int8 * Location, __int8 Value)  
  
```  
  
 **Parametreleri**  
  
 `Location`  
 Bir bellek konumunu okuma veya yazma için adresi.  
  
 `Value`(yalnızca iç bilgileri depolamak)  
 Belirtilen bellek konumuna yazılacak değer.  
  
 **Dönüş değeri (yalnızca yük iç bilgileri)**  
  
 Tarafından belirtilen bellek konumuna değerini `Location`.  
  
 **Açıklamalar**  
  
 Kullanabileceğiniz `__iso_volatile_load8/16/32/64` ve `__iso_volatile_store8/16/32/64` açıkça derleyici iyileştirmelerini tabi olmayan bellek erişimi gerçekleştirmek için iç bilgileri. Derleyici, synthetize, kaldırmak veya bu işlemlerin göreli sıralamasını değiştirmek, ancak örtük donanım bellek engelleri oluşturmaz. Bu nedenle, donanım observable bellek erişimleri birden çok iş parçacıkları arasında yeniden hala. Bu yapı daha hassas bir şekilde altında derlenmiş gibi aşağıdaki ifadeleri için eşdeğer **/volatile:iso**.  
  
```  
  
      int a = __iso_volatile_load32(p);    // equivalent to: int a = *(const volatile __int32*)p;   
__iso_volatile_store32(p, a);        // equivalent to: *(volatile __int32*)p = a;  
```  
  
 İç bilgiler geçici değişkenleri uyum sağlayacak şekilde volatile işaretçileri ele dikkat edin. Ancak, gereksinim veya volatile işaretçileri bağımsız değişken olarak kullanmak için öneri yoktur; Normal, geçici olmayan bir tür kullanılırsa, bu işlemlerin semantiği tam olarak aynı değildir.  
  
 Hakkında daha fazla bilgi için **/volatile:iso** komut satırı bağımsız değişkeni, bkz: [/volatile (volatile anahtar sözcük yorumu)](../build/reference/volatile-volatile-keyword-interpretation.md).  
  
###  <a name="MoveFromCo"></a>_MoveFromCoprocessor, _MoveFromCoprocessor2  
 Bu iç işlevler eşişlemcisi veri aktarımı yönergeleri kullanarak ARM coprocessors verileri okuyamadı.  
  
```  
int _MoveFromCoprocessor(  
      unsigned int coproc,  
      unsigned int opcode1,  
      unsigned int crn,  
      unsigned int crm,  
      unsigned int opcode2  
);  
  
int _MoveFromCoprocessor2(  
      unsigned int coproc,  
      unsigned int opcode1,  
      unsigned int crn,  
      unsigned int crm,  
      unsigned int opcode2  
);  
  
```  
  
 **Parametreleri**  
  
 `coproc`  
 0-15 aralığında eşişlemcisi sayı.  
  
 `opcode1`  
 Aralık 0 ile 7 içinde eşişlemcisi özgü işlem kodu  
  
 `crn`  
 Eşişlemcisi yönergesi için ilk işlenen belirten sayı, 0-15 aralıktaki kaydedin.  
  
 `crm`  
 Eşişlemcisi bir ek kaynak veya hedef işleneni belirten sayı, 0-15 aralıktaki kaydedin.  
  
 `opcode2`  
 Aralık 0 ile 7 ek eşişlemcisi özgü opcode.  
  
 **Dönüş değeri**  
  
 Eşişlemcisi okuma değeri.  
  
 **Açıklamalar**  
  
 Bu iç, tüm beş parametrelerinin değerlerini derleme zamanında bilinen sabit ifadeleri olmalıdır.  
  
 `_MoveFromCoprocessor`MRC yönerge kullanır; `_MoveFromCoprocessor2` MRC2 kullanır. Parametreleri doğrudan yönerge Word'e kodlanmış bit alanları karşılık gelir. Parametreleri yorumu eşişlemcisi bağımlıdır. Daha fazla bilgi için el ile ilgili eşişlemcisi için bkz.  
  
###  <a name="MoveFromCo64"></a>_MoveFromCoprocessor64  
 Eşişlemcisi veri aktarımı yönergeleri kullanarak ARM coprocessors verileri okur.  
  
```  
unsigned __int64 _MoveFromCoprocessor64(  
      unsigned int coproc,  
      unsigned int opcode1,  
      unsigned int crm,  
);  
  
```  
  
 **Parametreleri**  
  
 `coproc`  
 0-15 aralığında eşişlemcisi sayı.  
  
 `opcode1`  
 0-15 Aralık içinde eşişlemcisi özgü işlem kodu.  
  
 `crm`  
 Eşişlemcisi bir ek kaynak veya hedef işleneni belirten sayı, 0-15 aralıktaki kaydedin.  
  
 **Değeri döndürür**  
  
 Eşişlemcisi okuma değeri.  
  
 **Açıklamalar**  
  
 Bu iç, tüm üç parametre değerlerini derleme zamanında bilinen sabit ifadeleri olmalıdır.  
  
 `_MoveFromCoprocessor64`MRRC yönergesi kullanır. Parametreleri doğrudan yönerge Word'e kodlanmış bit alanları karşılık gelir. Parametreleri yorumu eşişlemcisi bağımlıdır. Daha fazla bilgi için el ile ilgili eşişlemcisi için bkz.  
  
###  <a name="MoveToCo"></a>_MoveToCoprocessor, _MoveToCoprocessor2  
 Bu iç işlevler eşişlemcisi veri aktarımı yönergeleri kullanarak ARM coprocessors için veri yazma.  
  
```  
void _MoveToCoprocessor(  
      unsigned int value,  
      unsigned int coproc,  
      unsigned int opcode1,  
      unsigned int crn,  
      unsigned int crm,  
      unsigned int opcode2  
);  
  
void _MoveToCoprocessor2(  
      unsigned int value,  
      unsigned int coproc,  
      unsigned int opcode1,  
      unsigned int crn,  
      unsigned int crm,  
      unsigned int opcode2  
);  
  
```  
  
 **Parametreleri**  
  
 `value`  
 Eşişlemcisi yazılacak değer.  
  
 `coproc`  
 0-15 aralığında eşişlemcisi sayı.  
  
 `opcode1`  
 Aralık 0 ile 7 içinde eşişlemcisi özgü işlem kodu.  
  
 `crn`  
 Eşişlemcisi yönergesi için ilk işlenen belirten sayı, 0-15 aralıktaki kaydedin.  
  
 `crm`  
 Eşişlemcisi bir ek kaynak veya hedef işleneni belirten sayı, 0-15 aralıktaki kaydedin.  
  
 `opcode2`  
 Aralık 0 ile 7 ek eşişlemcisi özgü opcode.  
  
 **Dönüş değeri**  
  
 Yok.  
  
 **Açıklamalar**  
  
 Değerlerini `coproc`, `opcode1`, `crn`, `crm`, ve `opcode2` bu iç parametrelerinin derleme zamanında bilinen sabit ifadeler olması gerekir.  
  
 `_MoveToCoprocessor`MCR yönerge kullanır; `_MoveToCoprocessor2` MCR2 kullanır. Parametreleri doğrudan yönerge Word'e kodlanmış bit alanları karşılık gelir. Parametreleri yorumu eşişlemcisi bağımlıdır. Daha fazla bilgi için el ile ilgili eşişlemcisi için bkz.  
  
###  <a name="MoveToCo64"></a>_MoveToCoprocessor64  
 Bu iç işlevler eşişlemcisi veri aktarımı yönergeleri kullanarak ARM coprocessors için veri yazma.  
  
```  
void _MoveFromCoprocessor64(  
      unsigned __int64 value,  
      unsigned int coproc,  
      unsigned int opcode1,  
      unsigned int crm,  
);  
  
```  
  
 **Parametreleri**  
  
 `coproc`  
 0-15 aralığında eşişlemcisi sayı.  
  
 `opcode1`  
 0-15 Aralık içinde eşişlemcisi özgü işlem kodu.  
  
 `crm`  
 Eşişlemcisi bir ek kaynak veya hedef işleneni belirten sayı, 0-15 aralıktaki kaydedin.  
  
 **Dönüş değeri**  
  
 Yok.  
  
 **Açıklamalar**  
  
 Değerlerini `coproc`, `opcode1`, ve `crm` bu iç parametrelerinin derleme zamanında bilinen sabit ifadeler olması gerekir.  
  
 `_MoveFromCoprocessor64`MCRR yönergesi kullanır. Parametreleri doğrudan yönerge Word'e kodlanmış bit alanları karşılık gelir. Parametreleri yorumu eşişlemcisi bağımlıdır. Daha fazla bilgi için el ile ilgili eşişlemcisi için bkz.  
  
##  <a name="I"></a>İç bilgiler diğer mimarileri gelen için ARM desteği  
 Aşağıdaki tabloda, ön tanımlı ARM platformlarında desteklenen diğer mimarileri gelen listeler. ARM üzerinde bir iç davranışını davranışını diğer donanım mimarileri üzerinde nerede farklıdır ek ayrıntılar belirtilmiştir.  
  
|İşlev adı|İşlev prototipi|  
|-------------------|------------------------|  
|__assume|void __assume(int)|  
|__code_seg|void __code_seg(const char *)|  
|__debugbreak|void __cdecl \__debugbreak(void)|  
|__fastfail|__declspec(noreturn) void \__fastfail (imzasız int)|  
|__nop|__nop(void) void **Not:** üzerinde ARM platformlar, bir hedef mimarisinde uygulanırsa, bu işlev bir NOP yönergesi oluşturur; Aksi halde, program veya CPU durumu değiştirmez alternatif bir yönerge oluşturulan — Örneğin, `MOV r8, r8`. Bu işlevsel olarak eşdeğerdir \__nop diğer donanım mimarileri için iç. Program veya CPU durumu üzerinde hiçbir etkisi olmaz bir yönerge bir iyileştirme olarak hedef mimarisi tarafından göz ardı nedeniyle talimat mutlaka CPU döngülerini sahip değil. Bu nedenle, kullanmayın \__nop CPU nasıl davranacağı hakkında olmadıkça bir kod dizisi yürütme süresini denetlemek için iç. Bunun yerine, kullanabileceğiniz \__nop belirli 32-bit sınır adresine sonraki yönerge hizalama iç.|  
|__yield|__yield(void) void **Not:** üzerinde ARM platformlar, bu işlev iş parçacığı yürütülmesini geçici olarak askıya alınacak bir görevi gerçekleştirme gösterir verim yönerge oluşturur — Örneğin, bir spinlock — olmadan program olumsuz etkileyen. Bu, aksi takdirde küçülttüğü iyi bir şekilde yürütme döngüsü sırasında diğer görevlerin yürütmek CPU sağlar.|  
|_AddressOfReturnAddress|void * _AddressOfReturnAddress(void)|  
|_BitScanForward|İmzasız char _BitScanForward (uzun imzasız * _Index, imzasız uzun _maskesi)|  
|_BitScanReverse|İmzasız char _BitScanReverse (uzun imzasız * _Index, imzasız uzun _maskesi)|  
|_bittest|İmzasız char _bittest (uzun const *, uzun)|  
|_bittestandcomplement|İmzasız char _bittestandcomplement (uzun *, uzun)|  
|_bittestandreset|İmzasız char _bittestandreset (uzun *, uzun)|  
|_bittestandset|İmzasız char _bittestandset (uzun *, uzun)|  
|_byteswap_uint64|İmzasız __int64 \__cdecl _byteswap_uint64 (imzasız \__int64)|  
|_byteswap_ulong|İmzasız uzun __cdecl _byteswap_ulong(unsigned long)|  
|_byteswap_ushort|İmzasız short __cdecl _byteswap_ushort (imzasız short)|  
|_disable|__cdecl _disable(void) void **Not:** ARM platformlarda bu işlev CPSID yönerge oluşturur; yalnızca bir iç kullanılabilir.|  
|_enable|__cdecl _enable(void) void **Not:** ARM platformlarda bu işlev CPSIE yönerge oluşturur; yalnızca bir iç kullanılabilir.|  
|_lrotl|İmzasız uzun __cdecl _lrotl (imzasız long, int)|  
|_lrotr|İmzasız uzun __cdecl _lrotr (imzasız long, int)|  
|_ReadBarrier|void _ReadBarrier(void)|  
|_ReadWriteBarrier|void _ReadWriteBarrier(void)|  
|_ReturnAddress|void * _ReturnAddress(void)|  
|_rotl|İmzasız int __cdecl _rotl (imzasız int _Value, int _Shift)|  
|_rotl16|İmzasız short _rotl16 (imzasız kısa _Value, imzasız char _Shift)|  
|_rotl64|İmzasız __int64 \__cdecl _rotl64 (imzasız \__int64 _Value, int _Shift)|  
|_rotl8|İmzasız char _rotl8 (imzasız char _Value, imzasız char _Shift)|  
|_rotr|İmzasız int __cdecl _rotr (imzasız int _Value, int _Shift)|  
|_rotr16|İmzasız short _rotr16 (imzasız kısa _Value, imzasız char _Shift)|  
|_rotr64|İmzasız __int64 \__cdecl _rotr64 (imzasız \__int64 _Value, int _Shift)|  
|_rotr8|İmzasız char _rotr8 (imzasız char _Value, imzasız char _Shift)|  
|_setjmpex|int __cdecl _setjmpex(jmp_buf)|  
|_WriteBarrier|void _WriteBarrier(void)|  
  
 [[NEON](#top)]  
  
## <a name="interlocked-intrinsics"></a>Interlocked iç bilgileri  
 Interlocked iç bilgileri atomik okuma-değiştirme-yazma işlemleri gerçekleştirmek için kullanılan iç bilgileri kümesidir. Bunlardan bazıları tüm platformlar için ortak olan. Bunlar ayrı olarak burada onları çok sayıda vardır, ancak tanımlarını çoğunlukla yedekli olduğundan, bunları hakkında genel koşulları düşündüğünüz daha kolaydır çünkü listelenir. Adları, tam davranışları türetmek için kullanılabilir.  
  
 Aşağıdaki tabloda olmayan-interlocked bittest ön tanımlı ARM desteği özetler. Tablodaki her hücre satırın en solundaki hücresindeki işlemi adını ve sütun için en üstteki hücrenin türü adını ekleyerek türetilmiş bir adına karşılık gelen `_Interlocked`. Örneğin, hücrenin kesişimindeki `Xor` satır ve **8** sütun karşılık gelen `_InterlockedXor8` ve tam olarak desteklenir. Desteklenen işlevlere çoğunu aşağıdaki isteğe bağlı soneklerini sunar: `_acq`, `_rel`, ve `_nf`. `_acq` Soneki belirten bir "Al" anlam ve `_rel` soneki bir "yayın" anlamsal gösterir. `_nf` Veya "dilimi yok" soneki ARM için benzersizdir ve sonraki bölümde açıklanmaktadır.  
  
||8|16|32|64|P|  
|-|-------|--------|--------|--------|-------|  
|Ekle|Yok.|Yok.|Tam|Tam|Yok.|  
|Ve|Tam|Tam|Tam|Tam|Yok.|  
|CompareExchange|Tam|Tam|Tam|Tam|Tam|  
|Azaltma|Yok.|Tam|Tam|Tam|Yok.|  
|Exchange|Kısmi|Kısmi|Kısmi|Kısmi|Kısmi|  
|ExchangeAdd|Tam|Tam|Tam|Tam|Yok.|  
|Artırma|Yok.|Tam|Tam|Tam|Yok.|  
|Veya|Tam|Tam|Tam|Tam|Yok.|  
|Xor|Tam|Tam|Tam|Tam|Yok.|  
  
 Anahtar:  
  
-   **Tam**: düz, destekler `_acq`, `_rel`, ve `_nf` forms.  
  
-   **Kısmi**: düz, destekler `_acq`, ve `_nf` forms.  
  
-   **Hiçbiri**: desteklenmiyor  
  
###  <a name="nf_suffix"></a>_nf (dilimi yok) soneki  
 `_nf` Veya işlemi bellek engeli olarak her türlü davranırlar değil "dilimi yok" soneki belirtir. Diğer üç forms aksine budur (düz, `_acq`, ve `_rel`), hangi tüm engel bazı tür davranır. Bir olası kullanımını `_nf` forms olduğundan, güncelleştirilir birden çok iş parçacığı tarafından aynı anda ancak değeri çoklu iş parçacığı yürütme sırasında Aksi halde kullanılmaz istatistiği sayaç korumak için.  
  
### <a name="list-of-interlocked-intrinsics"></a>Interlocked iç bilgi listesi  
  
|İşlev adı|İşlev prototipi|  
|-------------------|------------------------|  
|_Interlockedadd|uzun _ınterlockedadd (uzun _volatile *, uzun)|  
|_Interlockedadd64|__int64 _ınterlockedadd64 (\__int64 volatile *, \__int64)|  
|_Interlockedadd64_acq|__int64 _ınterlockedadd64_acq (\__int64 volatile *, \__int64)|  
|_Interlockedadd64_nf|__int64 _ınterlockedadd64_nf (\__int64 volatile *, \__int64)|  
|_Interlockedadd64_rel|__int64 _ınterlockedadd64_rel (\__int64 volatile *, \__int64)|  
|_Interlockedadd_acq|uzun _ınterlockedadd_acq (uzun volatile *, uzun)|  
|_Interlockedadd_nf|uzun _ınterlockedadd_nf (uzun volatile *, uzun)|  
|_Interlockedadd_nf|uzun _ınterlockedadd_nf (uzun volatile *, uzun)|  
|_InterlockedAnd|uzun _InterlockedAnd (uzun volatile *, uzun)|  
|_InterlockedAnd16|kısa _InterlockedAnd16 (kısa geçici *, kısa)|  
|_InterlockedAnd16_acq|kısa _InterlockedAnd16_acq (kısa geçici *, kısa)|  
|_InterlockedAnd16_nf|kısa _InterlockedAnd16_nf (kısa geçici *, kısa)|  
|_InterlockedAnd16_rel|kısa _InterlockedAnd16_rel (kısa geçici *, kısa)|  
|_InterlockedAnd64|__int64 _InterlockedAnd64 (\__int64 volatile *, \__int64)|  
|_InterlockedAnd64_acq|__int64 _InterlockedAnd64_acq (\__int64 volatile *, \__int64)|  
|_InterlockedAnd64_nf|__int64 _InterlockedAnd64_nf (\__int64 volatile *, \__int64)|  
|_InterlockedAnd64_rel|__int64 _InterlockedAnd64_rel (\__int64 volatile *, \__int64)|  
|_InterlockedAnd8|_InterlockedAnd8 char (char geçici *, char)|  
|_InterlockedAnd8_acq|_InterlockedAnd8_acq char (char geçici *, char)|  
|_InterlockedAnd8_nf|_InterlockedAnd8_nf char (char geçici *, char)|  
|_InterlockedAnd8_rel|_InterlockedAnd8_rel char (char geçici *, char)|  
|_InterlockedAnd_acq|uzun _InterlockedAnd_acq (uzun volatile *, uzun)|  
|_InterlockedAnd_nf|uzun _InterlockedAnd_nf (uzun volatile *, uzun)|  
|_InterlockedAnd_rel|uzun _InterlockedAnd_rel (uzun volatile *, uzun)|  
|_InterlockedCompareExchange|uzun __cdecl _InterlockedCompareExchange (uzun volatile * uzun, uzun)|  
|_InterlockedCompareExchange16|kısa _InterlockedCompareExchange16 (kısa geçici * kısa, kısa)|  
|_InterlockedCompareExchange16_acq|kısa _InterlockedCompareExchange16_acq (kısa geçici * kısa, kısa)|  
|_InterlockedCompareExchange16_nf|kısa _InterlockedCompareExchange16_nf (kısa geçici * kısa, kısa)|  
|_InterlockedCompareExchange16_rel|kısa _InterlockedCompareExchange16_rel (kısa geçici * kısa, kısa)|  
|_InterlockedCompareExchange64|__int64 _InterlockedCompareExchange64 (\__int64 volatile *, \__int64, \__int64)|  
|_InterlockedCompareExchange64_acq|__int64 _InterlockedCompareExchange64_acq (\__int64 volatile *, \__int64, \__int64)|  
|_InterlockedCompareExchange64_nf|__int64 _InterlockedCompareExchange64_nf (\__int64 volatile *, \__int64, \__int64)|  
|_InterlockedCompareExchange64_rel|__int64 _InterlockedCompareExchange64_rel (\__int64 volatile *, \__int64, \__int64)|  
|_InterlockedCompareExchange8|_InterlockedCompareExchange8 char (char geçici *, char, char)|  
|_InterlockedCompareExchange8_acq|_InterlockedCompareExchange8_acq char (char geçici *, char, char)|  
|_InterlockedCompareExchange8_nf|_InterlockedCompareExchange8_nf char (char geçici *, char, char)|  
|_InterlockedCompareExchange8_rel|_InterlockedCompareExchange8_rel char (char geçici *, char, char)|  
|_InterlockedCompareExchangePointer|void * _InterlockedCompareExchangePointer (void \* geçici \*, void \*, void \*)|  
|_InterlockedCompareExchangePointer_acq|void * _InterlockedCompareExchangePointer_acq (void \* geçici \*, void \*, void \*)|  
|_InterlockedCompareExchangePointer_nf|void * _InterlockedCompareExchangePointer_nf (void \* geçici \*, void \*, void \*)|  
|_InterlockedCompareExchangePointer_rel|void * _InterlockedCompareExchangePointer_rel (void \* geçici \*, void \*, void \*)|  
|_InterlockedCompareExchange_acq|uzun _InterlockedCompareExchange_acq (uzun volatile * uzun, uzun)|  
|_InterlockedCompareExchange_nf|uzun _InterlockedCompareExchange_nf (uzun volatile * uzun, uzun)|  
|_InterlockedCompareExchange_rel|uzun _InterlockedCompareExchange_rel (uzun volatile * uzun, uzun)|  
|_InterlockedDecrement|uzun __cdecl _InterlockedDecrement(long volatile *)|  
|_InterlockedDecrement16|kısa _InterlockedDecrement16(short volatile *)|  
|_InterlockedDecrement16_acq|kısa _InterlockedDecrement16_acq(short volatile *)|  
|_InterlockedDecrement16_nf|kısa _InterlockedDecrement16_nf(short volatile *)|  
|_InterlockedDecrement16_rel|kısa _InterlockedDecrement16_rel(short volatile *)|  
|_InterlockedDecrement64|__int64 _InterlockedDecrement64 (\__int64 volatile *)|  
|_InterlockedDecrement64_acq|__int64 _InterlockedDecrement64_acq (\__int64 volatile *)|  
|_InterlockedDecrement64_nf|__int64 _InterlockedDecrement64_nf (\__int64 volatile *)|  
|_InterlockedDecrement64_rel|__int64 _InterlockedDecrement64_rel (\__int64 volatile *)|  
|_InterlockedDecrement_acq|uzun _InterlockedDecrement_acq(long volatile *)|  
|_InterlockedDecrement_nf|uzun _InterlockedDecrement_nf(long volatile *)|  
|_InterlockedDecrement_rel|uzun _InterlockedDecrement_rel(long volatile *)|  
|_InterlockedExchange|uzun __cdecl _InterlockedExchange (uzun volatile * _Target, uzun)|  
|_InterlockedExchange16|kısa _InterlockedExchange16 (kısa geçici * _Target, kısa)|  
|_InterlockedExchange16_acq|kısa _InterlockedExchange16_acq (kısa geçici * _Target, kısa)|  
|_InterlockedExchange16_nf|kısa _InterlockedExchange16_nf (kısa geçici * _Target, kısa)|  
|_InterlockedExchange64|__int64 _InterlockedExchange64 (\__int64 volatile * _Target, \__int64)|  
|_InterlockedExchange64_acq|__int64 _InterlockedExchange64_acq (\__int64 volatile * _Target, \__int64)|  
|_InterlockedExchange64_nf|__int64 _InterlockedExchange64_nf (\__int64 volatile * _Target, \__int64)|  
|_InterlockedExchange8|_InterlockedExchange8 char (char geçici * _Target, char)|  
|_InterlockedExchange8_acq|_InterlockedExchange8_acq char (char geçici * _Target, char)|  
|_InterlockedExchange8_nf|_InterlockedExchange8_nf char (char geçici * _Target, char)|  
|_InterlockedExchangeAdd|uzun __cdecl _ınterlockedexchangeadd (uzun volatile *, uzun)|  
|_InterlockedExchangeAdd16|kısa _ınterlockedexchangeadd16 (kısa geçici *, kısa)|  
|_Interlockedexchangeadd16_acq|kısa _ınterlockedexchangeadd16_acq (kısa geçici *, kısa)|  
|_Interlockedexchangeadd16_nf|kısa _ınterlockedexchangeadd16_nf (kısa geçici *, kısa)|  
|_Interlockedexchangeadd16_rel|kısa _ınterlockedexchangeadd16_rel (kısa geçici *, kısa)|  
|_InterlockedExchangeAdd64|__int64 _ınterlockedexchangeadd64 (\__int64 volatile *, \__int64)|  
|_Interlockedexchangeadd64_acq|__int64 _ınterlockedexchangeadd64_acq (\__int64 volatile *, \__int64)|  
|_Interlockedexchangeadd64_nf|__int64 _ınterlockedexchangeadd64_nf (\__int64 volatile *, \__int64)|  
|_Interlockedexchangeadd64_rel|__int64 _ınterlockedexchangeadd64_rel (\__int64 volatile *, \__int64)|  
|_InterlockedExchangeAdd8|_ınterlockedexchangeadd8 char (char geçici *, char)|  
|_Interlockedexchangeadd8_acq|_ınterlockedexchangeadd8_acq char (char geçici *, char)|  
|_Interlockedexchangeadd8_nf|_ınterlockedexchangeadd8_nf char (char geçici *, char)|  
|_Interlockedexchangeadd8_rel|_ınterlockedexchangeadd8_rel char (char geçici *, char)|  
|_Interlockedexchangeadd_acq|uzun _ınterlockedexchangeadd_acq (uzun volatile *, uzun)|  
|_Interlockedexchangeadd_nf|uzun _ınterlockedexchangeadd_nf (uzun volatile *, uzun)|  
|_Interlockedexchangeadd_rel|uzun _ınterlockedexchangeadd_rel (uzun volatile *, uzun)|  
|_InterlockedExchangePointer|void * _InterlockedExchangePointer (void \* geçici \* _Target, void \*)|  
|_InterlockedExchangePointer_acq|void * _InterlockedExchangePointer_acq (void \* geçici \* _Target, void \*)|  
|_InterlockedExchangePointer_nf|void * _InterlockedExchangePointer_nf (void \* geçici \* _Target, void \*)|  
|_InterlockedExchange_acq|uzun _InterlockedExchange_acq (uzun volatile * _Target, uzun)|  
|_InterlockedExchange_nf|uzun _InterlockedExchange_nf (uzun volatile * _Target, uzun)|  
|_InterlockedIncrement|uzun __cdecl _InterlockedIncrement(long volatile *)|  
|_InterlockedIncrement16|kısa _InterlockedIncrement16(short volatile *)|  
|_InterlockedIncrement16_acq|kısa _InterlockedIncrement16_acq(short volatile *)|  
|_InterlockedIncrement16_nf|kısa _InterlockedIncrement16_nf(short volatile *)|  
|_InterlockedIncrement16_rel|kısa _InterlockedIncrement16_rel(short volatile *)|  
|_InterlockedIncrement64|__int64 _InterlockedIncrement64 (\__int64 volatile *)|  
|_InterlockedIncrement64_acq|__int64 _InterlockedIncrement64_acq (\__int64 volatile *)|  
|_InterlockedIncrement64_nf|__int64 _InterlockedIncrement64_nf (\__int64 volatile *)|  
|_InterlockedIncrement64_rel|__int64 _InterlockedIncrement64_rel (\__int64 volatile *)|  
|_InterlockedIncrement_acq|uzun _InterlockedIncrement_acq(long volatile *)|  
|_InterlockedIncrement_nf|uzun _InterlockedIncrement_nf(long volatile *)|  
|_InterlockedIncrement_rel|uzun _InterlockedIncrement_rel(long volatile *)|  
|_InterlockedOr|uzun _InterlockedOr (uzun volatile *, uzun)|  
|_InterlockedOr16|kısa _InterlockedOr16 (kısa geçici *, kısa)|  
|_InterlockedOr16_acq|kısa _InterlockedOr16_acq (kısa geçici *, kısa)|  
|_InterlockedOr16_nf|kısa _InterlockedOr16_nf (kısa geçici *, kısa)|  
|_InterlockedOr16_rel|kısa _InterlockedOr16_rel (kısa geçici *, kısa)|  
|_InterlockedOr64|__int64 _InterlockedOr64 (\__int64 volatile *, \__int64)|  
|_InterlockedOr64_acq|__int64 _InterlockedOr64_acq (\__int64 volatile *, \__int64)|  
|_InterlockedOr64_nf|__int64 _InterlockedOr64_nf (\__int64 volatile *, \__int64)|  
|_InterlockedOr64_rel|__int64 _InterlockedOr64_rel (\__int64 volatile *, \__int64)|  
|_InterlockedOr8|_InterlockedOr8 char (char geçici *, char)|  
|_InterlockedOr8_acq|_InterlockedOr8_acq char (char geçici *, char)|  
|_InterlockedOr8_nf|_InterlockedOr8_nf char (char geçici *, char)|  
|_InterlockedOr8_rel|_InterlockedOr8_rel char (char geçici *, char)|  
|_InterlockedOr_acq|uzun _InterlockedOr_acq (uzun volatile *, uzun)|  
|_InterlockedOr_nf|uzun _InterlockedOr_nf (uzun volatile *, uzun)|  
|_InterlockedOr_rel|uzun _InterlockedOr_rel (uzun volatile *, uzun)|  
|_InterlockedXor|uzun _InterlockedXor (uzun volatile *, uzun)|  
|_InterlockedXor16|kısa _InterlockedXor16 (kısa geçici *, kısa)|  
|_InterlockedXor16_acq|kısa _InterlockedXor16_acq (kısa geçici *, kısa)|  
|_InterlockedXor16_nf|kısa _InterlockedXor16_nf (kısa geçici *, kısa)|  
|_InterlockedXor16_rel|kısa _InterlockedXor16_rel (kısa geçici *, kısa)|  
|_InterlockedXor64|__int64 _InterlockedXor64 (\__int64 volatile *, \__int64)|  
|_InterlockedXor64_acq|__int64 _InterlockedXor64_acq (\__int64 volatile *, \__int64)|  
|_InterlockedXor64_nf|__int64 _InterlockedXor64_nf (\__int64 volatile *, \__int64)|  
|_InterlockedXor64_rel|__int64 _InterlockedXor64_rel (\__int64 volatile *, \__int64)|  
|_InterlockedXor8|_InterlockedXor8 char (char geçici *, char)|  
|_InterlockedXor8_acq|_InterlockedXor8_acq char (char geçici *, char)|  
|_InterlockedXor8_nf|_InterlockedXor8_nf char (char geçici *, char)|  
|_InterlockedXor8_rel|_InterlockedXor8_rel char (char geçici *, char)|  
|_InterlockedXor_acq|uzun _InterlockedXor_acq (uzun volatile *, uzun)|  
|_InterlockedXor_nf|uzun _InterlockedXor_nf (uzun volatile *, uzun)|  
|_InterlockedXor_rel|uzun _InterlockedXor_rel (uzun volatile *, uzun)|  
  
 [[NEON](#top)]  
  
### <a name="interlockedbittest-intrinsics"></a>_interlockedbittest iç bilgileri  
 Düz ınterlocked bittest iç bilgileri tüm platformlar için ortak olan. ARM ekler `_acq`, `_rel`, ve `_nf` yalnızca bir işlem engel semantiği açıklandığı şekilde değiştirmeniz çeşitleri [_nf (dilimi yok) soneki](#nf_suffix) bu makalenin önceki.  
  
|İşlev adı|İşlev prototipi|  
|-------------------|------------------------|  
|_interlockedbittestandreset|İmzasız char _interlockedbittestandreset (uzun volatile *, uzun)|  
|_interlockedbittestandreset_acq|İmzasız char _interlockedbittestandreset_acq (uzun volatile *, uzun)|  
|_interlockedbittestandreset_nf|İmzasız char _interlockedbittestandreset_nf (uzun volatile *, uzun)|  
|_interlockedbittestandreset_rel|İmzasız char _interlockedbittestandreset_rel (uzun volatile *, uzun)|  
|_interlockedbittestandset|İmzasız char _interlockedbittestandset (uzun volatile *, uzun)|  
|_interlockedbittestandset_acq|İmzasız char _interlockedbittestandset_acq (uzun volatile *, uzun)|  
|_interlockedbittestandset_nf|İmzasız char _interlockedbittestandset_nf (uzun volatile *, uzun)|  
|_interlockedbittestandset_rel|İmzasız char _interlockedbittestandset_rel (uzun volatile *, uzun)|  
  
 [[NEON](#top)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [ARM Assembler başvurusu](../assembler/arm/arm-assembler-reference.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)