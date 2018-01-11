---
title: inline_depth | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- inline_depth_CPP
- vc-pragma.inline_depth
dev_langs: C++
helpviewer_keywords:
- pragmas, inline_depth
- inline_depth pragma
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f105512910658603139105ecf1cf1d5b7030ad00
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="inlinedepth"></a>inline_depth
`n`'den daha büyük bir derinlikteyse (çağrı grafında) hiçbir işlevin satır içine alınmayacağı satır içi buluşsal arama derinliğini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma inline_depth( [n] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu pragma denetimleri işaretlenmiş işlevlerin satır içi kullanım [satır içi](../cpp/inline-functions-cpp.md) ve [__inline](../cpp/inline-functions-cpp.md) veya otomatik olarak /Ob2 seçeneği altında içermesinden.  
  
 `n` 0 ve 255 arasında bir değer olabilir; 255 çağrı grafiğinde sınırsız bir derinlik anlamına gelirken, sıfır satır içi genişletmeyi engeller.  `n` belirtilmezse, varsayılan (254) kullanılır.  
  
 **İnline_depth** pragma işlev çağrıları, bir dizi Genişletilebilir sayısını denetler. Örneğin, satır içi derinliği dört ise ve A B'yi çağırıyor ve B C'yi çağırıyorsa, üç çağrı da satır içinde genişletilir. Ancak, en yakın satır içi genişletme iki ise, yalnızca A ve B genişletilir ve C işlev çağrısı olarak kalır.  
  
 Bu pragmayı kullanmak için /Ob derleyici seçeneğini 1 veya 2'ye ayarlamanız gerekir. Bu pragma kullanılarak ayarlanan derinlik, pragmadan sonraki ilk işlev çağrısında etkin hale gelir.  
  
 Satır içi derinlik, genişletme sırasında azaltılabilir, ancak artırılmaz. Satır içi altı derinliğidir ve genişletme sırasında önişlemci karşılaşırsa bir **inline_depth** sekiz derinlik değerini pragma altı kalır.  
  
 **İnline_depth** pragma işlevleri ile işaretlenen hiçbir etkisi `__forceinline`.  
  
> [!NOTE]
>  Özyinelemeli işlevler, satır içinde en fazla 16 çağrılık bir derinlikle değiştirilebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline_recursion](../preprocessor/inline-recursion.md)