---
title: __svm_skinit
ms.date: 09/02/2019
f1_keywords:
- __svm_skinit
helpviewer_keywords:
- SKINIT instruction
- __svm_skinit intrinsic
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
ms.openlocfilehash: 6657921d647a23bf027a5800702527951f7f6831
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219860"
---
# <a name="__svm_skinit"></a>__svm_skinit

**Microsoft 'a özgü**

Bir sanal makine İzleyicisi gibi, güvenli yazılım yükleme işlemini başlatır.

## <a name="syntax"></a>Sözdizimi

```C
void __svm_skinit(
   int block_address
);
```

### <a name="parameters"></a>Parametreler

*block_address*\
64K baytlık güvenli yükleyici bloğunun 32 bitlik fiziksel adresi (SLB).

## <a name="remarks"></a>Açıklamalar

İşlev, `SKINIT` makine yönergesine eşdeğerdir. `__svm_skinit` Bu işlev, *güvenlik çekirdeği* (SK) olarak adlandırılan güvenilir yazılımları doğrulamak ve yüklemek için işlemciyi ve bir GÜVENILIR Platform Modülü (TPM) kullanan bir güvenlik sisteminin bir parçasıdır. Bir sanal makine İzleyicisi, güvenlik çekirdeğine bir örnektir. Güvenlik sistemi, başlatma işlemi sırasında yüklenen program bileşenlerini doğrular. Bilgisayar çok işlemcili ise, bileşenleri kesmeler, cihaz erişimi veya başka bir program tarafından değişikliklere karşı korur.

*Block_address* parametresi, *güvenli yükleyici bloğu* (SLB) olarak adlandırılan 64K bellek bloğunun fiziksel adresini belirtir. SLB, *güvenli yükleyici*adlı bir program içerir. Bilgisayar için işletim ortamını oluşturur ve ardından güvenlik çekirdeğini yükler.

Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, "AMD64 mimari programcı 'nin El Ile birim 2 ' yi aratın: Sistem programlama, " [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) sitesinde.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__svm_skinit`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
