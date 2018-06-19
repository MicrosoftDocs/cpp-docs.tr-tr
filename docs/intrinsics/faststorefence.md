---
title: __faststorefence | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __faststorefence_cpp
- __faststorefence
dev_langs:
- C++
helpviewer_keywords:
- __faststorefence intrinsic
- sfence instruction
ms.assetid: 6c6eb973-3cf0-4306-b3af-cfde9b0210a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f8c4a343126a14e1aea931b1e154714af280904
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33327804"
---
# <a name="faststorefence"></a>__faststorefence
**Microsoft özel**  
  
 Her ikisi de dahil olmak üzere her önceki bellek başvurusu yük ve bellek başvurularını depolamak garantileri önce herhangi bir sonraki bellek referans genel olarak görünür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __faststorefence();  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__faststorefence`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Garanti yüklemek ve işlemleri depolamak bir tam bellek engeli yönerge sırası oluşturur önce iç bu öğeler genel verilen yürütmeden önce görünür devam eder. Etkisi karşılaştırılabilir ancak daha hızlı bir şekilde `_mm_mfence` tüm x64 üzerinde iç platformlar.  
  
 AMD64 platformunda, bu yordamı daha hızlı bir depolama sınırı olan bir yönerge oluşturur `sfence` yönergesi. Zaman açısından kritik kod için yerine bu iç kullanmak `_mm_sfence` yalnızca AMD64 platformlarda. Intel x64 platformlarda `_mm_sfence` yönerge daha hızlı olması.  
  
 Bu yordam yalnızca bir iç kullanılabilir.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)