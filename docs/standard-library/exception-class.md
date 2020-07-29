---
title: exception Class
ms.date: 11/04/2016
f1_keywords:
- exception/std::exception
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
ms.openlocfilehash: fd3fb3c48e9501b7aaf90bca14ea98530b245ec0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228277"
---
# <a name="exception-class"></a>exception Class

Sınıfı, belirli ifadeler ve C++ standart kitaplığı tarafından oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.

## <a name="syntax"></a>Sözdizimi

```cpp
class exception {
   public:
   exception();
   exception(const char* const &message);
   exception(const char* const &message, int);
   exception(const exception &right);
   exception& operator=(const exception &right);
   virtual ~exception();
   virtual const char *what() const;
};
```

## <a name="remarks"></a>Açıklamalar

Özellikle, bu temel sınıf, içinde tanımlanan standart özel durum sınıflarının köküdür [\<stdexcept>](../standard-library/stdexcept.md) . Tarafından döndürülen C dize değeri `what` Varsayılan Oluşturucu tarafından belirtilmemiş, ancak uygulama tanımlı bir c dizesi olarak belirli türetilmiş sınıflar için oluşturucular tarafından tanımlanabilir. Üye işlevlerinin hiçbiri özel durum oluşturmaz.

**`int`** Parametresi, hiçbir belleğin ayrılmamalıdır belirtmenize izin verir. Değeri **`int`** yok sayılır.

> [!NOTE]
> Oluşturucular `exception(const char* const &message)` ve `exception(const char* const &message, int)` C++ standart kitaplığı için Microsoft uzantılarıdır.

## <a name="example"></a>Örnek

Sınıfından devraldığı standart özel durum sınıflarının kullanımı örnekleri için `exception` , içinde tanımlanan sınıflardan herhangi birine bakın [\<stdexcept>](../standard-library/stdexcept.md) .
