---
title: __thiscall
ms.date: 11/04/2016
f1_keywords:
- __thiscall
- __thiscall_cpp
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
ms.openlocfilehash: e51879ae62b2881e0adadbe59859605f6cc58947
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221916"
---
# <a name="thiscall"></a>__thiscall

**Microsoft'a özgü**

**__Thiscall** üye işlevlerde kullanılır ve çağırma kuralı tarafından kullanılan varsayılan çağırma kuralını C++ üye işlevleri, değişken bağımsız değişkenler kullanmayın. Altında **__thiscall**, çağrılan mümkün değildir yığını temizler `vararg` işlevleri. Bağımsız değişkenler itilir yığında sağdan sola, ile **bu** işaretçi ECX kayıt aracılığıyla ve x86 değil yığında geçirilen mimarisi.

Kullanmak için bir neden **__thiscall** sınıflar, üye işlevleri kullanımı olan `__clrcall` varsayılan olarak. Bu durumda, kullanabileceğiniz **__thiscall** üyesine çalıştığından yerel koddan çağrılabilir emin olmak için.

İle derlerken [/CLR: pure](../build/reference/clr-common-language-runtime-compilation.md), tüm işlevleri ve işlev işaretçileri `__clrcall` aksi belirtilmediği sürece. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Visual Studio 2005 önce sürümlerde **__thiscall** çağırma kuralı açıkça belirtilemedi bir programda çünkü **__thiscall** bir anahtar sözcük değildi.

`vararg` üye işlevleri kullanmak **__cdecl** çağırma kuralı. Tüm işlev bağımsız değişkenleri ile yığına itilir **bu** yerleştirilen işaretçi yığında son

Bu çağırma kuralı yalnızca C++ için geçerli olduğundan, hiçbir C ad düzenleme şeması yok.

ARM ve x64 makineler **__thiscall** kabul edilir ve derleyici tarafından yok sayılır.

Statik olmayan sınıf işlevleri için, işlev satır dışı olarak tanımlandıysa çağırma kuralı değiştiricinin satır dışı tanımda belirtilmesi gerekmez. Diğer bir deyişle, statik olmayan üye sınıfı yöntemler için tanım noktasında bildirim sırasında belirtilen çağırma kuralı kabul edilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)