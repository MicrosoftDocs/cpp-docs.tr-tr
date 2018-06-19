---
title: Derleyici Hatası C2567 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2567
dev_langs:
- C++
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05f89362f36a6ba576e9829153f0d8931c4975c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229695"
---
# <a name="compiler-error-c2567"></a>Derleyici Hatası C2567
meta verilerde 'dosya' açılamıyor, dosya taşınmış veya silinmiş  
  
 Kaynağında başvuruldu bir meta veri dosyası (ile `#using`) derleyici ön uç işlemiyle olduğu gibi aynı dizinde tarafından derleyici arka plan işlemi bulunamadı. Bkz: [#using yönergesi](../../preprocessor/hash-using-directive-cpp.md) daha fazla bilgi için.  
  
 İle derleme yaparsanız C2567 nedeni olabilir **/c** bir makine ve başka bir makine üzerinde bağlama zamanı kodu oluşturma denemesi. Daha fazla bilgi için bkz: [/LTCG (bağlama zamanı kodu oluşturma)](../../build/reference/ltcg-link-time-code-generation.md)).  
  
 Ayrıca, bilgisayarınız daha fazla bellek olduğunu gösterebilir.  
  
 Bu hatayı düzeltmek için meta veri dosyası oluşturma işlemi tüm aşamalar için dizin konumda olduğundan emin olun.