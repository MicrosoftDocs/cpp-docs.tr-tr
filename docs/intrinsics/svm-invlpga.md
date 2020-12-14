---
description: 'Hakkında daha fazla bilgi edinin: __svm_invlpga'
title: __svm_invlpga
ms.date: 09/02/2019
f1_keywords:
- __svm_invlpga
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
ms.openlocfilehash: dc976f535381fcfdfec0da5c1a280c4df281c114
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314756"
---
# <a name="__svm_invlpga"></a>__svm_invlpga

**Microsoft'a Özgü**

Bilgisayarın çeviri ara belleğine ait adres eşleme girişini geçersiz kılar. Parametreler geçersiz kılacak sayfanın sanal adresini ve adres alanı tanımlayıcısını belirtir.

## <a name="syntax"></a>Sözdizimi

```C
void __svm_invlpga(void *Vaddr, int as_id);
```

### <a name="parameters"></a>Parametreler

*Vaddr*\
'ndaki Geçersiz kılmak için sayfanın sanal adresi.

*as_id*\
'ndaki Geçersiz kılmak için sayfanın adres alanı tanımlayıcısı (ASıD).

## <a name="remarks"></a>Açıklamalar

`__svm_invlpga`İşlev, `INVLPGA` makine yönergesine eşdeğerdir. Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, "AMD64 mimari programcı 'nin El Ile Volume 2: sistem programlama," belge numarası 24593, düzeltme 3,11, sonra [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) sitesinde "belgeyi arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__svm_invlpga`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
