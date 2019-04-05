---
title: __svm_invlpga
ms.date: 11/04/2016
f1_keywords:
- __svm_invlpga
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
ms.openlocfilehash: 5e470fc12ad47aa156c513b293543fa356398d5e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031145"
---
# <a name="svminvlpga"></a>__svm_invlpga

**Microsoft'a Özgü**

Bilgisayarın çeviri görünüm edilgen arabellek adresi eşleme girişi geçersiz kılar. Adres alanı tanımlayıcısı geçersiz kılmak için sayfanın ve sanal adres parametreleri belirtin.

## <a name="syntax"></a>Sözdizimi

```
void __svm_invlpga(void *Va, int ASID);
```

#### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Va*|[in] Geçersiz kılmak için sayfanın sanal adres.|
|*ASID*|[in] Geçersiz kılmak için sayfanın adres alanı tanımlayıcısı (ASID).|

## <a name="remarks"></a>Açıklamalar

`__svm_invlpga` İşlev, eşdeğer `INVLPGA` makine yönergesi. Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Belge için daha fazla bilgi için arama "AMD64 mimarisi Programcı el ile birim 2: Sistem programlama,"belge numarasını 24593, düzeltme 3.11, adresindeki [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) site.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__svm_invlpga`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)