---
description: 'Daha fazla bilgi edinin: derleyici limitleri'
title: Derleyici Sınırları
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
ms.openlocfilehash: 7471b6e161f6e1f1466fdc27266249cefc17f7ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318162"
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
