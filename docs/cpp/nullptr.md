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
ms.openlocfilehash: dd7d7c9ccf70286040d06e7e01400299b806157e
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940985"
---
# <a name="nullptr"></a>nullptr
Bir boş işaretçi sabiti türü belirler `std::nullptr_t`, olan herhangi bir ham işaretçi türüne dönüştürülebilir.  Anahtar sözcüğünü kullanmanız mümkün olmakla birlikte **nullptr** kodunuzu türü kullanıyorsa, tüm üst bilgiler dahil olmadan `std::nullptr_t`, üst bilgisi ekleyerek tanımlamalıdır sonra `<cstddef>`.  
  
> [!NOTE]
>  **Nullptr** anahtar sözcüğü de tanımlanan C + +/ CLI için yönetilen kod uygulamaları ve ISO Standard C++ anahtar sözcüğü ile değiştirilebilir değildir. Kodunuzu kullanılarak derlenmiş, [/CLR](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği, yönetilen kod hedefler, ardından kullanmak `__nullptr` herhangi bir satırında kod burada gerekir garanti derleyici yerel C++ yorumu kullanır. Daha fazla bilgi için [nullptr](../windows/nullptr-cpp-component-extensions.md).  
  
## <a name="remarks"></a>Açıklamalar  
 NULL veya sıfır kullanmaktan kaçının (`0`) olarak; boş işaretçi sabiti **nullptr** kötüye kullanımı için daha az savunmasızdır ve çoğu durumda daha iyi çalışır.  Örneğin, verilen `func(std::pair<const char *, double>)`, ardından arama `func(std::make_pair(NULL, 3.14))` bir derleyici hatasına neden olur.  NULL genişletilir makrosu `0`, böylece çağrı `std::make_pair(0, 3.14)` döndürür `std::pair<int, double>`, func () olarak ın dönüştürülebilir değil `std::pair<const char *, double>` parametre türü.  Çağırma `func(std::make_pair(nullptr, 3.14))` başarıyla derlenir çünkü `std::make_pair(nullptr, 3.14)` döndürür `std::pair<std::nullptr_t, double>`, dönüştürülebilir olduğu `std::pair<const char *, double>`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)