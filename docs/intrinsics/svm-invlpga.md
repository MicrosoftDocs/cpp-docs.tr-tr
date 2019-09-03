---
title: __svm_invlpga
ms.date: 09/02/2019
f1_keywords:
- __svm_invlpga
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
ms.openlocfilehash: e0f8ef02efdb64f70bb65f6f017449fcc03beca1
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219893"
---
# <a name="__svm_invlpga"></a>__svm_invlpga

**Microsoft 'a özgü**

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

İşlev, `INVLPGA` makine yönergesine eşdeğerdir. `__svm_invlpga` Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için "AMD64 mimari programcı 'nin El Ile birim 2 ' yi arayın. Sistem programlama, "belge numarası 24593, düzeltme 3,11, [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) sitesinde.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__svm_invlpga`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
