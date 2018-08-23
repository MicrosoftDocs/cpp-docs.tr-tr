---
title: __svm_skinit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_skinit
dev_langs:
- C++
helpviewer_keywords:
- SKINIT instruction
- __svm_skinit intrinsic
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0912b7a1ff41bf7a21da198268dbd4b8dc920a9
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42466182"
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
  
 Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Belge için daha fazla bilgi için arama "AMD64 mimarisi Programcı el ile birim 2: Sistem programlama" konumundaki belge numarasını 24593, düzeltme 3.11, [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746) site.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__svm_skinit`|x86, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)