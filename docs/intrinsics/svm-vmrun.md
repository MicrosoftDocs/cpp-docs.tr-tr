---
title: __svm_vmrun
ms.date: 11/04/2016
f1_keywords:
- __svm_vmrun
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
ms.openlocfilehash: 40e53b2ebd54fc109b47f3067e5f89ce50b327de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390210"
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

`__svm_vmrun` İşlev, eşdeğer `VMRUN` makine yönergesi. Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Belge için daha fazla bilgi için arama "AMD64 mimarisi Programcı el ile birim 2: Belge numarasını 24593, düzeltme 3.11 ya da daha sonra sistem programlama," [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) site.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__svm_vmrun`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_vmsave](../intrinsics/svm-vmsave.md)<br/>
[__svm_vmload](../intrinsics/svm-vmload.md)