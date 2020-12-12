---
description: 'Daha fazla bilgi edinin: sınıflar ve yapılar (C++)'
title: Sınıflar ve Yapılar (C++)
ms.date: 05/07/2019
helpviewer_keywords:
- C++, classes and structs
ms.assetid: 516dd496-13fb-4f17-845a-e9ca45437873
ms.openlocfilehash: 9d845cf130c2cbf06e182a49f3d83c78745864d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114071"
---
# <a name="classes-and-structs-c"></a>Sınıflar ve Yapılar (C++)

Bu bölümde, C++ sınıfları ve yapıları tanıtılmaktadır. İki yapı, C++ ' da aynıdır, ancak sınıflar varsayılan olarak özeldir.

Sınıflar ve yapılar, kendi türlerinizi tanımladığınız yapılardır. Sınıfların ve yapıların her ikisi de, türün durumunu ve davranışını açıklamanıza olanak sağlayan veri üyeleri ve üye işlevleri içerebilir.

Aşağıdaki konular dahil edilmiştir:

- [sınıfı](../cpp/class-cpp.md)

- [sýný](../cpp/struct-cpp.md)

- [Sınıf üyesine genel bakış](../cpp/class-member-overview.md)

- [Üye Access Control](../cpp/member-access-control-cpp.md)

- [Devralma](../cpp/inheritance-cpp.md)

- [Statik Üyeler](../cpp/static-members-cpp.md)

- [Kullanıcı tanımlı tür dönüştürmeleri](../cpp/user-defined-type-conversions-cpp.md)

- [Değişebilir veri üyeleri (kesilebilir tanımlayıcı)](../cpp/mutable-data-members-cpp.md)

- [İç içe sınıf bildirimleri](../cpp/nested-class-declarations.md)

- [Anonim sınıf türleri](../cpp/anonymous-class-types.md)

- [Üye işaretçileri](../cpp/pointers-to-members.md)

- [Bu Işaretçi](../cpp/this-pointer.md)

- [C++ bit alanları](../cpp/cpp-bit-fields.md)

Üç sınıf türü yapı, sınıf ve birleşimdir. [Struct](../cpp/struct-cpp.md), [Class](../cpp/class-cpp.md)ve [Union](../cpp/unions.md) anahtar kelimeleri kullanılarak bildirilenler. Aşağıdaki tabloda, üç sınıf türü arasındaki farklılıklar gösterilmektedir.

Birleşimler hakkında daha fazla bilgi için bkz. [birleşimler](../cpp/unions.md). C++/CLı ve C++/CX içindeki sınıflar ve yapılar hakkında daha fazla bilgi için bkz. [sınıflar ve yapılar](../extensions/classes-and-structs-cpp-component-extensions.md).

### <a name="access-control-and-constraints-of-structures-classes-and-unions"></a>Yapıların, sınıfların ve birleşimlerin Access Control ve kısıtlamaları

|Yapılar|Sınıflar|Birleşimler|
|----------------|-------------|------------|
|sınıf anahtarı **`struct`**|sınıf anahtarı **`class`**|sınıf anahtarı **`union`**|
|Varsayılan erişim geneldir|Varsayılan erişim özeldir|Varsayılan erişim geneldir|
|Kullanım kısıtlaması yok|Kullanım kısıtlaması yok|Tek seferde yalnızca bir üye kullanın|

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](../cpp/cpp-language-reference.md)
