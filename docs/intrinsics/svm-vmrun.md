---
title: __svm_vmrun | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_vmrun
dev_langs:
- C++
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 718aba9b5ffe54edd3e9e960bd0530cd7b526b09
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394845"
---
# <a name="svmvmrun"></a>__svm_vmrun

**Microsoft'a özgü**

Belirtilen sanal makine denetim bloğu (VMCB) karşılık gelen sanal makine Konuk kod yürütmeyi başlatır.

## <a name="syntax"></a>Sözdizimi

```
void __svm_vmrun(
   size_t VmcbPhysicalAddress
);
```

#### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*VmcbPhysicalAddress*|[in] VMCB fiziksel adresi.|

## <a name="remarks"></a>Açıklamalar

`__svm_vmrun` İşlevi sanal makine Konuk kodu yürütmeye başlamak için VMCB içinde en az miktarda bilgi kullanır. Kullanım [__svm_vmsave](../intrinsics/svm-vmsave.md) veya [__svm_vmload](../intrinsics/svm-vmload.md) karmaşık kesmeyi işlemek için veya başka bir konuk geçiş yapmak için daha fazla bilgi gerekiyorsa işlev.

`__svm_vmrun` İşlev, eşdeğer `VMRUN` makine yönergesi. Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Belge için daha fazla bilgi için arama "AMD64 mimarisi Programcı el ile birim 2: Sistem programlama" belge numarasını 24593, düzeltme 3.11 ya da en üstü [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) site.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__svm_vmrun`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_vmsave](../intrinsics/svm-vmsave.md)<br/>
[__svm_vmload](../intrinsics/svm-vmload.md)