---
title: __if_not_exists deyimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __if_not_exists_cpp
dev_langs:
- C++
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd4e586a211d7c4e2ead1ce3f225e2d92d2bd5a7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 [__if_exists Deyimi](../cpp/if-exists-statement.md)