---
title: '&lt;stdexcept&gt;'
ms.date: 11/04/2016
f1_keywords:
- <stdexcept>
helpviewer_keywords:
- stdexcept header
ms.assetid: 495c10b1-1e60-4514-9f8f-7fda11a2f522
ms.openlocfilehash: 8a8c99f2651d10d4fc2aff413a06256127f32d7d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412507"
---
# <a name="ltstdexceptgt"></a>&lt;stdexcept&gt;

Raporlama özel durumlar için kullanılan bazı standart sınıfları tanımlar. Türetme hiyerarşi sınıftan türetilmiş tüm sınıfları form [özel durum](../standard-library/exception-class.md) ve özel durumları iki genel türleri şunlardır: mantıksal hataları ve çalışma zamanı hataları. Mantıksal hataları Programcı hatalarına neden olur. Bunlar, temel sınıf logic_error türetilir ve şunları içerir:

- `domain_error`

- `invalid_argument`

- `length_error`

- `out_of_range`

Kitaplık işlevleri veya çalışma zamanı sistemi hataları nedeniyle çalışma zamanı hataları oluşur. Bunlar, temel sınıf runtime_error türetilir ve şunları içerir:

- `overflow_error`

- `range_error`

- `underflow_error`

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[domain_error Sınıfı](../standard-library/domain-error-class.md)|Sınıfı, bir etki alanı hatayı bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[invalid_argument Sınıfı](../standard-library/invalid-argument-class.md)|Sınıfı, geçersiz bir bağımsız değişken bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[length_error Sınıfı](../standard-library/length-error-class.md)|Sınıfın belirtilmesi için çok uzun bir nesne oluşturma girişimi bildirmek için oluşturulan tüm özel durumlar için taban sınıf görevi görür.|
|[logic_error Sınıfı](../standard-library/logic-error-class.md)|Sınıf, mantıksal önkoşulları ihlalleri gibi program yürütülmeden önce büyük olasılıkla algılanabilir rapor hataları için oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.|
|[out_of_range Sınıfı](../standard-library/out-of-range-class.md)|Sınıfı, geçerli aralığın dışında bir bağımsız değişken bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[overflow_error Sınıfı](../standard-library/overflow-error-class.md)|Sınıfı, bir aritmetik taşma bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[range_error Sınıfı](../standard-library/range-error-class.md)|Sınıfı, bir aralık hatayı bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.|
|[runtime_error Sınıfı](../standard-library/runtime-error-class.md)|Sınıfı, programı yürütüldüğünde, büyük olasılıkla algılanabilir rapor hataları için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[underflow_error Sınıfı](../standard-library/underflow-error-class.md)|Sınıfı, bir aritmetik taşma bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
