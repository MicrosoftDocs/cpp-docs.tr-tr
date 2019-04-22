---
title: __svm_skinit
ms.date: 11/04/2016
f1_keywords:
- __svm_skinit
helpviewer_keywords:
- SKINIT instruction
- __svm_skinit intrinsic
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
ms.openlocfilehash: 199cba2623f9d8e47c08be642ec485599b87976e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026142"
---
# <a name="svmskinit"></a>__svm_skinit

**Microsoft'a özgü**

Bir sanal makine İzleyici gibi doğrulanabilir şekilde güvenli yazılım yüklemesini başlatır.

## <a name="syntax"></a>Sözdizimi

```
void __svm_skinit(
   int SLB
);
```

#### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`SLB`|Bir 64K bayt 32-bit fiziksel adresiyle yükleyici blok (SLB).|

## <a name="remarks"></a>Açıklamalar

`__svm_skinit` İşlev, eşdeğer `SKINIT` makine yönergesi. Bu işlev, doğrulama ve güvenlik çekirdek (SK) adlı güvenilir yazılımları yüklemek için işlemci ve Güvenilir Platform Modülü (TPM) kullanan bir güvenlik sistemi bir parçasıdır. Bir sanal makine izleme, güvenlik çekirdek örneğidir. Güvenlik sistemi program bileşenleri başlatma sırasında yüklenen ve bileşenleri çok işlemcili bilgisayar ise kesme, cihaz erişim veya başka bir program tarafından izinsiz kullanıma karşı korur doğrular.

`SLB` Parametresi, bir 64K olarak adlandırılan bellek bloğu fiziksel adresini belirtir *güvenli yükleyici blok* (SLB). SLB bilgisayarın işletim sistemi ortamında oluşturur ve daha sonra güvenlik çekirdek yükler güvenli yükleyici adlı bir programı içerir.

Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Belge için daha fazla bilgi için arama "AMD64 mimarisi Programcı el ile birim 2: Sistem programlama,"belge numarasını 24593, düzeltme 3.11, adresindeki [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) site.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__svm_skinit`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)