---
description: 'Hakkında daha fazla bilgi edinin: Derleyici COM destek sınıfları'
title: Derleyici COM Desteği Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
ms.openlocfilehash: e2f921e9c3ebe759109d741630afe56f6af30bbc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344711"
---
# <a name="compiler-com-support-classes"></a>Derleyici COM Desteği Sınıfları

**Microsoft'a Özgü**

Standart sınıflar, bazı COM türlerini desteklemek için kullanılır. Sınıfları \<comdef.h> ve tür kitaplığından oluşturulan üstbilgi dosyalarını ve içinde tanımlanır.

|Sınıf|Amaç|
|-----------|-------------|
|[_bstr_t](../cpp/bstr-t-class.md)|`BSTR`Yararlı işleçler ve Yöntemler sağlamak için türü kaydırır.|
|[_com_error](../cpp/com-error-class.md)|En fazla hatalarda [_com_raise_error](../cpp/com-raise-error.md) tarafından oluşturulan hata nesnesini tanımlar.|
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|COM arabirimi işaretçilerini kapsüller ve,, ve için gerekli çağrıları `AddRef` otomatikleştirir `Release` `QueryInterface` .|
|[_variant_t](../cpp/variant-t-class.md)|`VARIANT`Yararlı işleçler ve Yöntemler sağlamak için türü kaydırır.|

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM desteği](../cpp/compiler-com-support.md)<br/>
[Derleyici COM genel Işlevleri](../cpp/compiler-com-global-functions.md)<br/>
[C++ dil başvurusu](../cpp/cpp-language-reference.md)
