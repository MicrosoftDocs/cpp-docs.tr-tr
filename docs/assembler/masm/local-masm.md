---
title: YEREL (MASM) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Local
dev_langs:
- C++
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed9926d23f2e1e8636f31a6f586609ae22d38acd
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32053577"
---
# <a name="local-masm"></a>LOCAL (MASM)
Makro içinde ilk yönergesinde **yerel** makrosu her örneği için benzersiz etiketleri tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      LOCAL localname [[, localname]]...  
LOCAL label [[ [count ] ]] [[:type]] [[, label [[ [count] ]] [[type]]]]...  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir yordamı tanımı içinde ikinci yönergesi (**PROC**), **yerel** yordam boyunca mevcut yığın tabanlı değişkenleri oluşturur. *Etiket* basit bir değişken veya bir dizi içeren olabilir *sayısı* öğeleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)