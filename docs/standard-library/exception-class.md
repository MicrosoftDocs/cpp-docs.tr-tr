---
description: 'Daha fazla bilgi edinin: özel durum sınıfı'
title: exception Class
ms.date: 11/04/2016
f1_keywords:
- exception/std::exception
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
ms.openlocfilehash: a2061a2609017872145b12b4863e939788a123cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324455"
---
# <a name="exception-class"></a>exception Class

Sınıfı, belirli ifadeler ve C++ standart kitaplığı tarafından oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.

## <a name="syntax"></a>Syntax

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
