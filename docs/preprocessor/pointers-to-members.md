---
title: pointers_to_members | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- pointers_to_members_CPP
- vc-pragma.pointers_to_members
dev_langs:
- C++
helpviewer_keywords:
- class members, pointers to
- pragmas, pointers_to_members
- members, pointers to
- pointers_to_members pragma
ms.assetid: 8325428c-c90a-4aed-9e82-cb1dda23f4ca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4313aaa38d410b8e6f46594cd9ce11269b523073
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="pointerstomembers"></a>pointers_to_members
**C++ özel**  
  
 Bir sınıf üyesinin işaretçisinin, ilişkilendirilmiş sınıf tanımından önce bildirilip bildirilemeyeceğini ve işaretçi boyutunu ve işaretçiyi yorumlamak için gerekli kodu denetlemek için kullanılıp kullanılmadığını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma pointers_to_members( pointer-declaration, [most-general-representation] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Yerleştireceğiniz bir **pointers_to_members** kullanmaya alternatif olarak, kaynak dosyanızdaki pragma [/vmx](../build/reference/vmb-vmg-representation-method.md) derleyici seçenekleri veya [devralınan anahtar sözcükler](../cpp/inheritance-keywords.md).  
  
 *İşaretçi bildirimi* bağımsız değişkeni, bir işaretçi bir üyesine önce veya sonra ilişkili işlev tanımı bildirilen olup olmadığını belirtir. *İşaretçi bildirimi* bağımsız değişkeni aşağıdaki iki simge biridir:  
  
|Bağımsız Değişken|Açıklamalar|  
|--------------|--------------|  
|**full_generality**|Güvenli, bazen uygun durumda olmayan kod üretir. Kullandığınız **full_generality** herhangi bir üye işaretçisine önce ilişkili sınıf tanımını bildirilirse. Bu bağımsız değişkeni tarafından belirtilen işaretçi gösterimini her zaman kullanır *en genel gösterimi* bağımsız değişkeni. /vmg ile eşdeğerdir.|  
|**best_case**|Tüm üye işaretçileri için best-case gösterimini kullanılarak güvenli, en iyi durumda kod oluşturur. Sınıfın bir üyesinin işaretçisini bildirmeden önce sınıfın tanımlanmasını gerektirir. Varsayılan değer **best_case**.|  
  
 *En genel gösterimi* bağımsız değişkeni derleyici güvenle herhangi bir çeviri biriminde bir sınıf üyesi işaretçisine başvurmak için kullanabileceğiniz en küçük işaretçi gösterimi belirtir. Bağımsız değişken aşağıdakilerden biri olabilir:  
  
|Bağımsız Değişken|Açıklamalar|  
|--------------|--------------|  
|**single_inheritance**|En genel gösterim, bir üye işlevi işaretçisi olan single-inheritance'tır. Kendisi için bir üye işaretçisinin bildirildiği bir sınıf tanımının devralma modeli birden çok veya sanal ise hataya neden olur.|  
|**multiple_inheritance**|En genel gösterim, bir üye işlev işaretçisi olan multiple-inheritance'tır. Kendisi için bir üye işaretçisinin bildirildiği bir sınıf tanımının devralma modeli sanal ise hataya neden olur.|  
|**virtual_inheritance**|En genel devralma, bir üye işlev işaretçisi olan virtual-inheritance'tır. Hiçbir zaman hataya neden olmaz. Bu varsayılan bağımsız değişken değer olduğunda **#pragma pointers_to_members(full_generality)** kullanılır.|  
  
> [!CAUTION]
>  `pointers_to_members` pragmasını yalnızca etkilemek istediğiniz kaynak kod dosyasına ve `#include` yönergelerinden sonra yerleştirmenizi öneririz. Bu uygulama, pragmanın başka dosyaları etkileme riskini ve aynı değişken, işlev veya sınıf adı için yanlışlıkla birden fazla tanım belirtme olasılığınızı azaltır.  
  
## <a name="example"></a>Örnek  
  
```  
//   Specify single-inheritance only  
#pragma pointers_to_members( full_generality, single_inheritance )  
```  
  
## <a name="end-c-specific"></a>Son C++ özel  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)