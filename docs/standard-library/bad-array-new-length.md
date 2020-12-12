---
description: 'Hakkında daha fazla bilgi edinin: bad_array_new_length sınıfı'
title: bad_array_new_length sınıfı
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_array_new_length
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: e9de10b6fee215651ac8ff6ce2fce4af55ce6c82
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321646"
---
# <a name="bad_array_new_length-class"></a>bad_array_new_length sınıfı

Sınıf, sıfırdan küçük veya sınırından büyük bir ayırma isteğinin başarılı olmadığını göstermek için oluşturulan bir özel durumu açıklar.

## <a name="syntax"></a>Syntax

```cpp
class bad_array_new_length : public bad_alloc {
    public: bad_array_new_length() noexcept;
    const char* what() const noexcept override;
};
```

## <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer, `what` uygulama tanımlı bir C dizesidir. Üye işlevlerinin hiçbiri özel durum oluşturmaz.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<new>

## <a name="see-also"></a>Ayrıca bkz.

[özel durum sınıfı](../standard-library/exception-class.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
