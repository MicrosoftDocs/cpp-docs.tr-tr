---
title: Derleyici Sınırları
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
ms.openlocfilehash: e0e2381d88c727466b06a97c72826d2d5e15a87b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233775"
---
# <a name="compiler-limits"></a>Derleyici Sınırları

C++ standardı çeşitli dil yapıları için sınırlar önerir. Aşağıda, Microsoft C++ derleyicisinin önerilen sınırları uygulamayan durumların bir listesi verilmiştir. İlk sayı ISO C++ 11 standardında (ıNITS/ISO/ıEC 14882-2011 [2012], ek B) ve ikinci sayının Microsoft C++ derleyicisi tarafından uygulanan sınırın üzerinde kurulduğu limidir:

- Bileşik deyimlerin, yineleme denetim yapılarının ve seçim denetimi yapılarının iç içe geçirilmesi-C++ standart: 256, Microsoft C++ derleyicisi: iç içe geçmiş deyimlerin birleşimine bağlıdır, ancak genellikle 100 ve 110 arasındadır.

- Bir makro tanımındaki parametreler-C++ standart: 256, Microsoft C++ derleyicisi: 127.

- Bir makro çağrısında bağımsız değişkenler-C++ standart: 256, Microsoft C++ derleyicisi 127.

- Karakter dizesi sabit değerindeki veya geniş dize sabit değerindeki (birleştirme sonrası) karakterler-C++ standart: 65536, Microsoft C++ derleyicisi: 65535 tek baytlık karakterler, null Sonlandırıcı dahil, ve NULL Sonlandırıcı dahil olmak üzere 32767 çift baytlı karakterler.

- Tek C++ standardında iç içe sınıf, yapı veya birleşim tanımlarının düzeyleri `struct-declaration-list` : 256, Microsoft C++ derleyicisi: 16.

- Bir Oluşturucu tanımındaki üye başlatıcıları-C++ standart: 6144, Microsoft C++ derleyicisi: en az 6144.

- Bir tanımlayıcının kapsam nitelikleri-C++ standart: 256, Microsoft C++ derleyicisi: 127.

- İç içe **`extern`** belirtimler-C++ standart: 1024, Microsoft C++ derleyicisi: 9 (genel kapsamda örtülü **`extern`** Belirtim sayılmaz veya genel kapsamda örtük belirtimi saymanız halinde 10 **`extern`** .

- Şablon bildiriminde şablon bağımsız değişkenleri-C++ standart: 1024, Microsoft C++ derleyicisi: 2046.

## <a name="see-also"></a>Ayrıca bkz.

[Standart olmayan davranış](../cpp/nonstandard-behavior.md)
