---
title: __svm_stgi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_stgi
dev_langs:
- C++
helpviewer_keywords:
- __svm_stgi intrinsic
- STGI instruction
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd4d2593621c7c2cc36f84580a757e98f5e48c92
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431261"
---
# <a name="svmstgi"></a>__svm_stgi

**Microsoft'a özgü**

Genel kesme bayrağını ayarlar.

## <a name="syntax"></a>Sözdizimi

```
void __svm_stgi(void);
```

## <a name="remarks"></a>Açıklamalar

`__svm_stgi` İşlev, eşdeğer `STGI` makine yönergesi. Genel kesme bayrağı mikro yoksayar, erteler veya kesme olayları gibi bir g/ç tamamlama, donanım sıcaklık uyarı veya hata ayıklama özel durumu nedeniyle işleme belirler.

Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Belge için daha fazla bilgi için arama "AMD64 mimarisi Programcı el ile birim 2: Sistem programlama" konumundaki belge numarasını 24593, düzeltme 3.11, [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) site.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__svm_stgi`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_clgi](../intrinsics/svm-clgi.md)