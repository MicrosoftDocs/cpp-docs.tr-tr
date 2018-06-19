---
title: Derleyici Hatası C2338 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2338
dev_langs:
- C++
helpviewer_keywords:
- C2338
ms.assetid: 49bba575-1de4-4963-86c6-ce3226a2ba51
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 156074f20517c1d2e2f4fdb4ac5c54d6cf014276
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33222312"
---
# <a name="compiler-error-c2338"></a>Derleyici Hatası C2338  
  
> *Hata iletisi*  
  
Bu hatanın nedeni bir `static_assert` derleme sırasında bir hata oluştu. İleti tarafından sağlanan `static_assert` parametreleri.   
  
Bu hata iletisini derleyici dış sağlayıcıları tarafından da oluşturulabilir. Çoğu durumda, bu hataları özniteliği sağlayıcısını DLL ATLPROV gibi tarafından raporlanır. Bu iletinin bazı ortak formlar şunları içerir:

> '*özniteliği*' Atl özniteliği sağlayıcısı: hata ATL*numarası* *iletisi*  
  
> Öznitelik yanlış kullanımı '*özniteliği*'
  
> '*kullanım*': 'kullanımı' özniteliği için yanlış biçim  
  
Bu hatalar genellikle kurtarılamaz ve önemli derleyici hatası tarafından takip edilebilir.  
  
Bu sorunları düzeltmek için öznitelik kullanımı düzeltin. Örneğin, kullanılabilmesi için önce bazı durumlarda, öznitelik parametreleri bildirilmesi gerekir. ATL hata numarası sağlanmazsa, daha fazla bilgi için hata belgelerini denetleyin.  
