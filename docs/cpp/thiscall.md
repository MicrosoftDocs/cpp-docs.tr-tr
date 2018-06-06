---
title: __thiscall | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __thiscall
- __thiscall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4912628529ae0b47a5a5b938ab8e6d25a9099510
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704409"
---
# <a name="thiscall"></a>__thiscall

**Microsoft özel**

`__thiscall` Çağırma üye işlevlerini kullanılır ve değişken bağımsız değişken kullanmayın C++ üye işlevleri tarafından kullanılan varsayılan çağırma. Altında `__thiscall`, aranan olanaksız yığını temizler `vararg` işlevleri. Bağımsız değişkenler kalan yığında sağdan sola, ile `this` kayıt ECX aracılığıyla ve yığında x86 değil, geçirilen işaretçi mimarisi.

Kullanmak için bir neden `__thiscall` olan üye işlevlerini kullanmak sınıflarda olduğu `__clrcall` varsayılan olarak. Bu durumda, kullanabileceğiniz `__thiscall` tek tek üye işlevleri yerel koddan aranabilir yapma.

İle derleme yapılırken [/CLR: pure](../build/reference/clr-common-language-runtime-compilation.md), tüm işlevleri ve işlev işaretçileri `__clrcall` aksi belirtilmediği sürece. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

Visual C++ 2005 önce sürümlerde `__thiscall` çağırma kuralı açıkça belirtilemedi bir programda çünkü `__thiscall` bir anahtar sözcük değildi.

`vararg` üye işlevlerini kullanmak `__cdecl` çağırma. Tüm işlev bağımsız değişkenleri, ile yığına `this` işaretçi yerleştirilen yığında son

Bu çağırma yalnızca C++ için geçerli olduğundan, hiçbir C adı decoration düzeni yoktur.

ARM ve x64 makineler, `__thiscall` kabul edilir ve derleyici tarafından yoksayıldı.

Statik olmayan sınıf işlevleri için, işlev satır dışı olarak tanımlandıysa çağırma kuralı değiştiricinin satır dışı tanımda belirtilmesi gerekmez. Diğer bir deyişle, statik olmayan üye sınıfı yöntemler için tanım noktasında bildirim sırasında belirtilen çağırma kuralı kabul edilir.

**SON Microsoft özel**

## <a name="see-also"></a>Ayrıca bkz.

- [Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)
