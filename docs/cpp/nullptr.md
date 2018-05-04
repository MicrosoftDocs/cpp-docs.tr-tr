---
title: nullptr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- nullptr_cpp
dev_langs:
- C++
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1bcfee3f408f6815e51740f9fc02d842afaa4d5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="nullptr"></a>nullptr
Türünde bir null işaretçinin sabit atar `std::nullptr_t`, olduğu herhangi bir ham işaretçi türüne dönüştürülebilir.  Anahtar sözcüğünü kullanabilirsiniz ancak `nullptr` türü kodunuzu kullanıyorsa, tüm üstbilgileri dahil olmak üzere olmadan `std::nullptr_t`, üstbilgi dahil ederek tanımlamanız gerekir sonra `<cstddef>`.  
  
> [!NOTE]
>  `nullptr` Anahtar sözcüğü de tanımlanabilir C + +/ CLI için yönetilen kod uygulamaları ve ISO standart C++ anahtar sözcüğüyle birbirinin yerine değil. Kodunuzu kullanarak derlenmiş ise [/CLR](../build/reference/clr-common-language-runtime-compilation.md) yönetilen kod hedefler, derleyici seçeneği sonra kullanın `__nullptr` herhangi satırında kod burada gerekir garanti derleyici yerel C++ yorumlama kullanır. Daha fazla bilgi için bkz: [nullptr](../windows/nullptr-cpp-component-extensions.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanmaktan kaçının `NULL` veya sıfır (`0`) olarak bir null işaretçinin sabit; `nullptr` kötüye kullanılması için daha az savunmasızdır ve çoğu durumda daha iyi çalışır.  Örneğin, verilen `func(std::pair<const char *, double>)`, ardından çağırma `func(std::make_pair(NULL, 3.14))` derleyici hatasına neden olur.  NULL genişletir için makrosu `0`, böylece çağrı `std::make_pair(0, 3.14)` döndürür `std::pair<int, double>`, func () için 's dönüştürülebilir olmayan `std::pair<const char *, double>` parametre türü.  Çağırma `func(std::make_pair(nullptr, 3.14))` başarıyla derlenir çünkü `std::make_pair(nullptr, 3.14)` döndürür `std::pair<std::nullptr_t, double>`, dönüştürülebilir olduğu `std::pair<const char *, double>`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)