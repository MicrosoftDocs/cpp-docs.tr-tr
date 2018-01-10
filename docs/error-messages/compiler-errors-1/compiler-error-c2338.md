---
title: "Derleyici Hatası C2338 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2338
dev_langs: C++
helpviewer_keywords: C2338
ms.assetid: 49bba575-1de4-4963-86c6-ce3226a2ba51
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0171654bde5b056a7e6695ea5fbbe84edb62f83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
