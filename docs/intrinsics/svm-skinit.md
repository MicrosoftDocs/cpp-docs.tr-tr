---
description: 'Hakkında daha fazla bilgi edinin: __svm_skinit'
title: __svm_skinit
ms.date: 09/02/2019
f1_keywords:
- __svm_skinit
helpviewer_keywords:
- SKINIT instruction
- __svm_skinit intrinsic
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
ms.openlocfilehash: dd35566664a6bff4a57ea986fc99ffcd731c79e2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206272"
---
# <a name="__svm_skinit"></a>__svm_skinit

**Microsoft'a Özgü**

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

`__svm_skinit`İşlev, `SKINIT` makine yönergesine eşdeğerdir. Bu işlev, *güvenlik çekirdeği* (SK) olarak adlandırılan güvenilir yazılımları doğrulamak ve yüklemek için işlemciyi ve bir GÜVENILIR Platform Modülü (TPM) kullanan bir güvenlik sisteminin bir parçasıdır. Bir sanal makine İzleyicisi, güvenlik çekirdeğine bir örnektir. Güvenlik sistemi, başlatma işlemi sırasında yüklenen program bileşenlerini doğrular. Bilgisayar çok işlemcili ise, bileşenleri kesmeler, cihaz erişimi veya başka bir program tarafından değişikliklere karşı korur.

*Block_address* parametresi, *güvenli yükleyici bloğu* (SLB) olarak adlandırılan 64K bellek bloğunun fiziksel adresini belirtir. SLB, *güvenli yükleyici* adlı bir program içerir. Bilgisayar için işletim ortamını oluşturur ve ardından güvenlik çekirdeğini yükler.

Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) SITESINDE "AMD64 Architecture Programmer 'ın el ile Volume 2: sistem programlama" ifadesini aratın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__svm_skinit`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
