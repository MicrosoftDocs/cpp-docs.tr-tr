---
title: Derleyici COM Desteği Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
ms.openlocfilehash: 1a9ff7c57965c9ba00881d5fe48501a6138b31d1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444425"
---
# <a name="compiler-com-support-classes"></a>Derleyici COM Desteği Sınıfları

**Microsoft 'a özgü**

Standart sınıflar, bazı COM türlerini desteklemek için kullanılır. Sınıflar, tür kitaplığından oluşturulan \<Comdef. h > ve üst bilgi dosyalarında tanımlanır.

|Sınıf|Amaç|
|-----------|-------------|
|[_bstr_t](../cpp/bstr-t-class.md)|`BSTR` türünü, faydalı işleçler ve Yöntemler sağlamak üzere sarar.|
|[_com_error](../cpp/com-error-class.md)|En fazla hatalarda [_com_raise_error](../cpp/com-raise-error.md) tarafından oluşturulan hata nesnesini tanımlar.|
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|COM arabirimi işaretçilerini kapsüller ve `AddRef`, `Release`ve `QueryInterface`için gerekli çağrıları otomatikleştirir.|
|[_variant_t](../cpp/variant-t-class.md)|`VARIANT` türünü, faydalı işleçler ve Yöntemler sağlamak üzere sarar.|

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM Desteği](../cpp/compiler-com-support.md)<br/>
[Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)