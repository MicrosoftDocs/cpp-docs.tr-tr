---
title: Sınıflar ve yapılar (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, classes
- structures, C++ classes
- user-defined types
- classes [C++]
- user-defined types, C++ classes
ms.assetid: 516dd496-13fb-4f17-845a-e9ca45437873
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fbe9991807d1572504bbaa0f4e903e46cac1766a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058646"
---
# <a name="classes-and-structs-c"></a>Sınıflar ve Yapılar (C++)

Bu bölüm, C++ sınıfları ve yapıları tanıtır. İki yapıları, sınıflarda varsayılan özel iken yapılar için varsayılan erişilebilirlik genel dışında C++ ile aynıdır.

Sınıflar ve yapılar kendi türlerinizi yapabildiği tanımladığınız yapılarıdır. Sınıflar ve yapılar hem de veri üyeleri ve türün durumunu ve davranışını açıklamak etkinleştirdiğiniz üye işlevlerini içerebilir.

Aşağıdaki konular bulunur:

- [class](../cpp/class-cpp.md)

- [struct](../cpp/struct-cpp.md)

- [Sınıf Üyelerine Genel bakış](../cpp/class-member-overview.md)

- [Üye Erişim Denetimi](../cpp/member-access-control-cpp.md)

- [Devralma](../cpp/inheritance-cpp.md)

- [Statik Üyeler](../cpp/static-members-cpp.md)

- [Kullanıcı Tanımlı Tür Dönüşümleri](../cpp/user-defined-type-conversions-cpp.md)

- [Değişebilir veri üyeleri (değişebilir tanımlayıcı)](../cpp/mutable-data-members-cpp.md)

- [İç İçe Geçmiş Sınıf Bildirimleri](../cpp/nested-class-declarations.md)

- [Anonim Sınıf Türleri](../cpp/anonymous-class-types.md)

- [Üye İşaretçileri](../cpp/pointers-to-members.md)

- [this İşaretçisi](../cpp/this-pointer.md)

- [C++ Bit Alanları](../cpp/cpp-bit-fields.md)

Üç sınıf yapısı, sınıf ve union türleridir. Kullanılarak bildirilirler [yapı](../cpp/struct-cpp.md), [sınıfı](../cpp/class-cpp.md), ve [birleşim](../cpp/unions.md) anahtar sözcükleri. Aşağıdaki tabloda, üç sınıf türleri arasındaki farklar gösterilmektedir.

Birleşimler hakkında daha fazla bilgi için bkz. [birleşimler](../cpp/unions.md). Yönetilen sınıflar ve yapı birimleri hakkında daha fazla bilgi için bkz: [sınıfları ve yapıları](../windows/classes-and-structs-cpp-component-extensions.md).

### <a name="access-control-and-constraints-of-structures-classes-and-unions"></a>Erişim denetimi ve kısıtlamalar yapıları, sınıflar ve birleşimler

|Yapılar|Sınıflar|Birleşimler|
|----------------|-------------|------------|
|sınıf anahtarı **yapısı**|sınıf anahtarı **sınıfı**|sınıf anahtarı **birleşim**|
|Varsayılan erişimi geneldir|Özel varsayılan erişim|Varsayılan erişimi geneldir|
|Hiçbir kullanım kısıtlamaları|Hiçbir kullanım kısıtlamaları|Bir kerede yalnızca bir üyesini kullanın|

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)