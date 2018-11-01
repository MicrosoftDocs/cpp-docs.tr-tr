---
title: Derleyici Sınırları
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
ms.openlocfilehash: a0c6041d326982dc9807355733cf714dcfa62ca8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50600336"
---
# <a name="compiler-limits"></a>Derleyici Sınırları

C++ standartı, çeşitli dil yapıları için sınırlar önerir. Burada Visual C++ derleyicisi, önerilen sınırları uygulamıyor örneklerinin listesi verilmiştir. ISO C++ 11'de standart (INCITS/ISO/IEC 14882-2011 [2012] Annex B) belirlenen sınırı ilk sayıdır ve ikinci sayı Visual C++ tarafından uygulanan sınır:

- Bileşik deyimler, yineleme kontrol yapılarını ve seçim iç içe geçme düzeyi denetim yapıları - C++ Standart: 256, Visual C++ derleyicisi: birleşimi iç içe geçmiş deyimler ancak genellikle 110 ile 100 arasındaki bağlıdır.

- Bir Makro tanımında - C++ Standart Parametreler: 256, Visual C++ derleyicisi: 127.

- Bir makro çağrısı - C++ standart bağımsız değişkenleri: 256, Visual C++ derleyicisi 127.

- Bir karakterin karakter dize sabit değeri veya geniş dize değişmez değeri (birleştirmesi sonra) - C++ Standart: 65536, Visual C++ derleyicisi: NULL sonlandırıcıyı da dahil olmak üzere, 65535 tek baytlık karakter ve NULL Sonlandırıcı dahil olmak üzere, 32767 çift baytlık karakterler.

- İç içe geçmiş sınıf, yapı veya birleşim tanımlarına tek bir düzeyde `struct-declaration-list` -C++ Standart: 256, Visual C++ derleyicisi: 16.

- Bir oluşturucu tanımı - C++ Standart üyesi başlatıcıları: 6144, Visual C++ derleyicisi: en az 6144.

- Bir tanımlayıcının - C++ Standart nitelikleri kapsam: 256, Visual C++ derleyicisi: 127.

- İç içe geçmiş **extern** belirtimleri - C++ Standart: 1024, Visual C++ derleyicisi: 9 (örtük sayılmaz **extern** belirtimi genel kapsamda veya 10 örtük sayısı, **extern**  belirtimi genel kapsamda...

- Bir şablon bildiriminde - C++ standart şablon bağımsız değişkenleri: 1024, Visual C++ derleyicisi: 2046.

## <a name="see-also"></a>Ayrıca bkz.

[Standart Olmayan Davranış](../cpp/nonstandard-behavior.md)