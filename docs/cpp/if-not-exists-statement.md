---
title: __if_not_exists deyimi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: __if_not_exists_cpp
dev_langs: C++
helpviewer_keywords: __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5bd11ed833b54082d7ea2a394bdd4cad3c3e1321
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ifnotexists-statement"></a>__if_not_exists Deyimi
`__if_not_exists` Deyimi belirtilen tanımlayıcı var olup olmadığını sınar. Tanımlayıcı mevcut değilse, belirtilen ifade bloğu yürütülür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__if_not_exists ( identifier ) {   
statements  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`identifier`|Varlığı test etmek istediğiniz tanımlayıcısı.|  
|`statements`|Varsa yürütmek için bir veya daha fazla deyimleri `identifier` yok.|  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!CAUTION]
>  En güvenilir sonuçlar elde etmek için kullanmak `__if_not_exists` deyimi aşağıdaki kısıtlamalar altında.  
  
-   Uygulama `__if_not_exists` deyimi yalnızca basit türlere, şablon yok.  
  
-   Uygulama `__if_not_exists` deyimi içinde veya dışında bir sınıf tanımlayıcıları. Geçerli `__if_not_exists` yerel değişkenler ifadesine.  
  
-   Kullanım `__if_not_exists` deyimi yalnızca bir işlev gövdesi. Bir işlev gövdesi dışında `__if_not_exists` deyimi tam olarak tanımlı türler yalnızca test edebilirsiniz.  
  
-   Aşırı yüklenen işlevler için test ettiğinizde, belirli bir aşırı yük form için test edilemez.  
  
 Tamamlayan `__if_not_exists` ifadesi [__if_exists](../cpp/if-exists-statement.md) deyimi.  
  
## <a name="example"></a>Örnek  
 Bir örneğin nasıl kullanılacağı hakkında `__if_not_exists`, bkz: [__if_exists deyimi](../cpp/if-exists-statement.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seçim deyimleri](../cpp/selection-statements-cpp.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [__if_exists deyimi](../cpp/if-exists-statement.md)