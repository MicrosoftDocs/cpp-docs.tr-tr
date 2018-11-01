---
title: exception Class
ms.date: 11/04/2016
f1_keywords:
- exception
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
ms.openlocfilehash: 009ef74d810976eb9f054b45e388ceb0fe612b2e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521048"
---
# <a name="exception-class"></a>exception Class

Sınıfı, belirli ifadeler ve C++ Standart Kitaplığı tarafından oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.

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

Özellikle, taban sınıfı içinde tanımlanan standart özel durum sınıfları köküdür [ \<stdexcept >](../standard-library/stdexcept.md). C dize tarafından döndürülen değeri `what` sol varsayılan oluşturucu tarafından belirtilmemiş olan ancak bir uygulama tanımlı C dizesi olarak belirli bir türetilmiş sınıflara ilişkin oluşturucular tarafından tanımlanabilir. Üye işlevlerinin hiçbiri, tüm özel durumlar.

**İnt** parametre bellek ayrılması gereken belirtmenize olanak tanır. Değerini **int** göz ardı edilir.

> [!NOTE]
> Oluşturucular `exception(const char* const &message)` ve `exception(const char* const &message, int)` C++ Standart Kitaplığı, Microsoft uzantılarıdır.

## <a name="example"></a>Örnek

Devralınan standart özel durum sınıfları kullanım örnekleri için `exception` sınıfı, hiç tanımlanan sınıfların [ \<stdexcept >](../standard-library/stdexcept.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<özel durum >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
