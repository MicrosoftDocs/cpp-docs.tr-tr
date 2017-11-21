---
title: "Sınıflar ve yapılar (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- Visual C++, classes
- structures, C++ classes
- user-defined types
- classes [C++]
- user-defined types, C++ classes
ms.assetid: 516dd496-13fb-4f17-845a-e9ca45437873
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0d5f690846954dde21252b2aabdd229abdf33ec6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="classes-and-structs-c"></a>Sınıflar ve Yapılar (C++)
Bu bölüm, C++ sınıfları ve yapıları tanıtır. Sınıflarda varsayılan özel iken yapılar için varsayılan erişilebilirlik ortak olması dışında iki yapıları C++ ile aynıdır.  
  
 Sınıflar ve yapılar kendi türlerinizi tanımlama yapabildiği yapıları var. Sınıflar ve yapılar hem de veri üyeleri ve tür durumunu ve davranışını tanımlamak etkinleştirmeniz üye işlevleri içerebilir.  
  
 Aşağıdaki konular bulunur:  
  
-   [sınıfı](../cpp/class-cpp.md)  
  
-   [yapısı](../cpp/struct-cpp.md)  
  
-   [Sınıf üyelerine genel bakış](../cpp/class-member-overview.md)  
  
-   [Üye erişim denetimi](../cpp/member-access-control-cpp.md)  
  
-   [Devralma](../cpp/inheritance-cpp.md)  
  
-   [Statik üyeler](../cpp/static-members-cpp.md)  
  
-   [Kullanıcı tanımlı tür dönüşümleri](../cpp/user-defined-type-conversions-cpp.md)  
  
-   [Değişebilir veri üyeleri (değişebilir tanımlayıcı)](../cpp/mutable-data-members-cpp.md)  
  
-   [İç içe geçmiş sınıf bildirimleri](../cpp/nested-class-declarations.md)  
  
-   [Anonim sınıf türleri](../cpp/anonymous-class-types.md)  
  
-   [Üye işaretçileri](../cpp/pointers-to-members.md)  
  
-   [this işaretçisi](../cpp/this-pointer.md)  
  
-   [C++ Bit alanları](../cpp/cpp-bit-fields.md)  
  
 Üç sınıf yapısı, sınıf ve birleşim türleridir. Kullanılarak bildirilir [yapısı](../cpp/struct-cpp.md), [sınıfı](../cpp/class-cpp.md), ve [UNION](../cpp/unions.md) anahtar sözcükler (bkz [sınıf türleri tanımlama](http://msdn.microsoft.com/en-us/e8c65425-0f3a-4dca-afc2-418c3b1e57da)). Aşağıdaki tabloda, üç sınıf türleri arasındaki farklar gösterilmektedir.  
  
 Birleşimler hakkında daha fazla bilgi için bkz: [birleşimler](../cpp/unions.md). Yönetilen sınıflar ve yapılar hakkında daha fazla bilgi için bkz: [sınıflar ve yapılar](../windows/classes-and-structs-cpp-component-extensions.md).  
  
### <a name="access-control-and-constraints-of-structures-classes-and-unions"></a>Erişim denetimi ve kısıtlamaları yapılar, sınıflar ve birleşimler  
  
|Yapılar|Sınıflar|Birleşimler|  
|----------------|-------------|------------|  
|sınıf anahtarı`struct`|sınıf anahtarı **sınıfı**|sınıf anahtarı **birleşimi**|  
|Varsayılan erişim ortak|Varsayılan erişim özeldir|Varsayılan erişim ortak|  
|Hiçbir kullanım kısıtlamaları|Hiçbir kullanım kısıtlamaları|Aynı anda yalnızca bir üye kullanın|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)