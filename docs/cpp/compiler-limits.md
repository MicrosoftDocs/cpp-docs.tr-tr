---
title: Derleyici Sınırları
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
ms.openlocfilehash: 9e61cae1638c87f03b6fa775552408961bde6859
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189588"
---
# <a name="compiler-limits"></a>Derleyici Sınırları

C++ Standart çeşitli dil yapıları için sınırlar önerir. Aşağıda, Microsoft C++ derleyicisinin önerilen sınırları uygulamayan durumların bir listesi verilmiştir. İlk sayı ISO C++ 11 standardında (ıNITS/ISO/IEC 14882-2011 [2012], ek B) ve Ikinci sayının Microsoft C++ derleyicisi tarafından uygulanan sınırın üzerinde kurulduğu limidir:

- Bileşik deyimlerin, yineleme denetim yapılarının ve seçim denetimi yapılarının iç içe geçirilmesi- C++ standart: 256, Microsoft C++ derleyicisi: iç içe geçmiş deyimlerin birleşimine bağlıdır, ancak genellikle 100 ve 110 arasındadır.

- Tek bir makro tanımındaki parametreler- C++ standart: 256, Microsoft C++ derleyicisi: 127.

- Tek makro çağrısı içindeki bağımsız değişkenler C++ -standart: 256, C++ Microsoft derleyicisi 127.

- Karakter dizesi değişmez değeri veya geniş dize sabit değerindeki karakterler (birleştirme sonrasında)- C++ standart: 65536, Microsoft C++ derleyicisi: 65535 tek baytlık karakterler, null SONLANDıRıCı dahil, ve null sonlandırıcı dahil olmak üzere 32767 çift baytlık karakterler.

- Tek bir `struct-declaration-list` C++ standart: 256, Microsoft C++ derleyicisi: 16 içinde iç içe sınıf, yapı veya birleşim tanımlarının düzeyleri.

- Oluşturucu tanımında üye başlatıcıları- C++ standart: 6144, Microsoft C++ derleyicisi: en az 6144.

- Bir tanımlayıcının kapsam nitelikleri- C++ standart: 256, Microsoft C++ derleyicisi: 127.

- İç **extern** içe olmayan dış C++ özellikler-standart: 1024 C++ , Microsoft derleyicisi: 9 (genel **kapsamda örtük** **extern** belirtimini saymanız ya da 10.

- Şablon bildiriminde şablon bağımsız değişkenleri- C++ standart: 1024, Microsoft C++ derleyicisi: 2046.

## <a name="see-also"></a>Ayrıca bkz.

[Standart Olmayan Davranış](../cpp/nonstandard-behavior.md)
