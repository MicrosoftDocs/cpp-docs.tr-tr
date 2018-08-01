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
ms.openlocfilehash: bee63ace276863a30c4ec81d970ba3bf5fd29e40
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405291"
---
# <a name="ifnotexists-statement"></a>__if_not_exists Deyimi
**__İf_not_exists** deyimi belirtilen tanımlayıcı var olup olmadığını test eder. Tanımlayıcı mevcut değilse, belirtilen deyim bloğu yürütülür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__if_not_exists ( identifier ) {   
statements  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*tanımlayıcı*|Test etmek istediğiniz varlığı tanımlayıcısı.|  
|*Deyimleri*|Bir veya daha fazla deyimlerini *tanımlayıcı* yok.|  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!CAUTION]
>  En güvenilir sonuçlar elde etmek için kullanın **__if_not_exists** deyiminin altında aşağıdaki kısıtlamalar geçerlidir.  
  
-   Uygulama **__if_not_exists** deyimi yalnızca basit türlere, şablon yok.  
  
-   Uygulama **__if_not_exists** deyimi içinde veya dışında bir sınıf tanımlayıcıları. Geçerli **__if_not_exists** yerel değişkenlere deyimi.  
  
-   Kullanım **__if_not_exists** deyimi yalnızca bir işlev gövdesinin içinde. Bir işlev gövdesinin dışında **__if_not_exists** deyimi tam olarak tanımlanmamış türlerden yalnızca test edebilirsiniz.  
  
-   Aşırı yüklenmiş işlevler için test ettiğinizde, belirli bir aşırı yükleme form için test edilemez.  
  
 Tamamlayan **__if_not_exists** deyimi [__if_exists](../cpp/if-exists-statement.md) deyimi.  
  
## <a name="example"></a>Örnek  
 Nasıl kullanılacağı hakkında bir örnek **__if_not_exists**, bkz: [__if_exists deyimi](../cpp/if-exists-statement.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Seçim deyimleri](../cpp/selection-statements-cpp.md)   
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [__if_exists Deyimi](../cpp/if-exists-statement.md)