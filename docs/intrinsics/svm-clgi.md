---
title: __svm_clgi
ms.date: 11/04/2016
f1_keywords:
- __svm_clgi
helpviewer_keywords:
- CLGI instruction
- __svm_clgi intrinsic
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
ms.openlocfilehash: fe25141499a19a265e2ac3ec746664ecd6cc9a2e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59028703"
---
# <a name="svmclgi"></a>__svm_clgi

**Microsoft'a Özgü**

Genel kesme bayrağını kaldırır.

## <a name="syntax"></a>Sözdizimi

```
void __svm_clgi( void );
```

## <a name="remarks"></a>Açıklamalar

`__svm_clgi` İşlev, eşdeğer `CLGI` makine yönergesi. Genel kesme bayrağı mikro yoksayar, erteler veya kesme olayları gibi bir g/ç tamamlama, donanım sıcaklık uyarı veya hata ayıklama özel durumu nedeniyle işleme belirler.

Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Belge için daha fazla bilgi için arama "AMD64 mimarisi Programcı el ile birim 2: Sistem programlama,"belge numarasını 24593, düzeltme 3.11, adresindeki [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) site.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__svm_clgi`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_stgi](../intrinsics/svm-stgi.md)