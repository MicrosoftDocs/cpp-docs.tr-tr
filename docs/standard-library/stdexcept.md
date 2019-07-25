---
title: '&lt;stdexcept&gt;'
ms.date: 11/04/2016
f1_keywords:
- <stdexcept>
helpviewer_keywords:
- stdexcept header
ms.assetid: 495c10b1-1e60-4514-9f8f-7fda11a2f522
ms.openlocfilehash: d4028d57a6e8898f85a37d9731e7e8d4cda19a2f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453718"
---
# <a name="ltstdexceptgt"></a>&lt;stdexcept&gt;

Özel durum bildirmek için kullanılan birkaç standart sınıfı tanımlar. Sınıflar sınıf [özel](../standard-library/exception-class.md) durumundan türetilmiş bir türetme hiyerarşisi oluşturur ve iki genel özel durum türü içerir: mantıksal hatalar ve çalışma zamanı hataları. Mantıksal hatalar programcı hatalarına neden oldu. Bunlar, logic_error temel sınıfından türetilir ve şunları içerir:

- `domain_error`

- `invalid_argument`

- `length_error`

- `out_of_range`

Çalışma zamanı hataları, kitaplık işlevlerinde veya çalışma zamanı sisteminde hatalar nedeniyle oluşur. Bunlar, runtime_error temel sınıfından türetilir ve şunları içerir:

- `overflow_error`

- `range_error`

- `underflow_error`

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[domain_error Sınıfı](../standard-library/domain-error-class.md)|Sınıfı, bir etki alanı hatasını raporlamak için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[invalid_argument Sınıfı](../standard-library/invalid-argument-class.md)|Sınıfı, geçersiz bir bağımsız değişkeni raporlamak için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[length_error Sınıfı](../standard-library/length-error-class.md)|Sınıfı, belirtilene çok uzun bir nesne oluşturma girişimini raporlamak için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[logic_error Sınıfı](../standard-library/logic-error-class.md)|Sınıfı, program yürütmeden önce, mantıksal önkoşulların ihlalleri gibi, hataları bildirmek üzere oluşan tüm özel durumlar için temel sınıf görevi görür.|
|[out_of_range Sınıfı](../standard-library/out-of-range-class.md)|Sınıfı, geçerli aralığının dışında bir bağımsız değişkeni raporlamak için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[overflow_error Sınıfı](../standard-library/overflow-error-class.md)|Sınıfı, aritmetik taşma bildirmek üzere oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[range_error Sınıfı](../standard-library/range-error-class.md)|Sınıfı, bir Aralık hatası bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[runtime_error Sınıfı](../standard-library/runtime-error-class.md)|Sınıfı, yalnızca program yürütüldüğünde oluşan hataları raporlamak için oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.|
|[underflow_error Sınıfı](../standard-library/underflow-error-class.md)|Sınıfı, aritmetik bir alt sınırın raporlanmak üzere oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
