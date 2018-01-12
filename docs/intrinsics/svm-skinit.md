---
title: __svm_skinit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __svm_skinit
dev_langs: C++
helpviewer_keywords:
- SKINIT instruction
- __svm_skinit intrinsic
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e02bafc9319a6a3a4c5e07b46c9da6586f440d59
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="svmskinit"></a>__svm_skinit
**Microsoft özel**  
  
 Bir sanal makine izleme gibi doğrulanabilir şekilde güvenli yazılım yüklemesini başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __svm_skinit(  
   int SLB  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`SLB`|Bir 64K bayt 32-bit fiziksel adresini güvenli yükleyicisi blok (SLB).|  
  
## <a name="remarks"></a>Açıklamalar  
 `__svm_skinit` İşlevi eşdeğerdir `SKINIT` makine yönergesi. Bu işleve doğrulayın ve güvenlik çekirdek (SK) adı verilen güvenilir yazılım yüklemek için işlemci ve Güvenilir Platform Modülü (TPM) kullanan bir güvenlik sistemi bir parçasıdır. Bir sanal makine izleme, güvenlik çekirdek örneğidir. Güvenlik sistemi program bileşenleri başlatma işlemi sırasında yüklenen ve bir çok işlemcili bilgisayarsa kesmeleri, cihaz erişimi veya başka bir program tarafından müdahale etmesini bileşenleri korur doğrular.  
  
 `SLB` Parametresi olarak adlandırılan bellek 64K bloğunu fiziksel adresini belirtir *güvenli yükleyicisi blok* (SLB). SLB bilgisayarı işletim ortamını oluşturan ve daha sonra güvenlik çekirdek yükler güvenli yükleyicisi adlı bir programı içerir.  
  
 Bu işlev bir ana bilgisayarın sanal makine İzleyici etkileşiminin bir konuk işletim sistemi ve uygulamaları destekler. Daha fazla bilgi için belge için arama "AMD64 mimarisi Programcı el ile birim 2: Sistem programlama" konumundaki belge numarasını 24593, düzeltme 3.11, [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746) site.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__svm_skinit`|x86,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)