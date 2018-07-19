---
title: özel durum sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- exception
dev_langs:
- C++
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec1cfe2be7f6a2172b6624f15cb3dcde4f0ba3c2
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957024"
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
