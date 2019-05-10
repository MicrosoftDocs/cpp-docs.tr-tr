---
title: Derleyici Sınırları
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
ms.openlocfilehash: 9663da06c97886ef1cd20ca2928944795b39dc18
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222200"
---
# <a name="compiler-limits"></a>Derleyici Sınırları

C++ standartı, çeşitli dil yapıları için sınırlar önerir. Aşağıdaki durumlarda listesidir burada Microsoft C++ derleyici önerilen sınırları uygulamıyor. ISO belirlenen sınırı ilk sayıdır C++ 11 standart (INCITS/ISO/IEC 14882-2011 [2012] Annex B) ve ikinci sayı Microsoft tarafından uygulanan sınır C++ derleyici:

- Bileşik deyimler, yineleme kontrol yapılarını ve seçim denetim yapıları - iç içe geçme düzeyi C++ standart: 256, Microsoft C++ derleyici: birleşimi iç içe geçmiş deyimler ancak genellikle 110 ile 100 arasındaki bağlıdır.

- Parametreleri bir Makro tanımında - C++ standart: 256, Microsoft C++ derleyici: 127.

- Bir makro çağrısı - değişkenlerinde C++ standart: 256, Microsoft C++ derleyici 127.

- Bir karakterin karakter dize sabit değeri veya geniş dize değişmez değeri (birleştirmesi sonra) - C++ standart: 65536, Microsoft C++ derleyici: NULL sonlandırıcıyı da dahil olmak üzere, 65535 tek baytlık karakter ve NULL Sonlandırıcı dahil olmak üzere, 32767 çift baytlık karakterler.

- İç içe geçmiş sınıf, yapı veya birleşim tanımlarına tek bir düzeyde `struct-declaration-list` - C++ standart: 256, Microsoft C++ derleyici: 16.

- Bir oluşturucu tanımı - üyesi başlatıcıları C++ standart: 6144, Microsoft C++ derleyici: en az 6144.

- Bir tanımlayıcının - nitelikleri kapsam C++ standart: 256, Microsoft C++ derleyici: 127.

- İç içe geçmiş **extern** belirtimleri - C++ standart: 1024, Microsoft C++ derleyici: 9 (örtük sayılmaz **extern** belirtimi genel kapsamda veya 10 örtük sayısı, **extern** belirtimi genel kapsamda..

- Şablon bağımsız değişkenleri bir şablon bildiriminde - C++ standart: 1024, Microsoft C++ derleyici: 2046.

## <a name="see-also"></a>Ayrıca bkz.

[Standart Olmayan Davranış](../cpp/nonstandard-behavior.md)