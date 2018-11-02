---
title: Derleyici Hatası C3505
ms.date: 11/04/2016
f1_keywords:
- C3505
helpviewer_keywords:
- C3505
ms.assetid: ed73c99e-93a1-4f3a-bac7-ba7ed5d836e4
ms.openlocfilehash: 5730102371d00ebaf3ae05fdefb70184b58d7c18
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481785"
---
# <a name="compiler-error-c3505"></a>Derleyici Hatası C3505

> tür kitaplığı yüklenemiyor '*GUID*'

C3505 32-bit, x86 barındırılan çapraz derleyici 64-bit çalıştırıyorsanız neden olabilir, 64 bit hedef makine derleyici WOW64 altında çalıştığından ve yalnızca x64 32-bit kayıt defteri kovanından okuyun.

Almaya çalıştığınız tür kitaplığını hem 32-bit hem de 64 bit sürümlerini oluşturarak bu hatayı gidermek ve ardından her ikisinin de kaydedin.  Veya değiştirmenizi gerektirir yerel 64 bit derleyiciyi kullanabilirsiniz, **VC ++ dizinleri** için 64 bit derleyici işaret edecek şekilde IDE özelliği.

Daha fazla bilgi için bkz:

- [Nasıl yapılır: Komut Satırında 64 Bit Visual C++ Araç Takımını Etkinleştirme](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)

- [Nasıl Yapılır: Visual C++ Projelerinin 64 Bit, x64 Platformları Hedeflemesi için Yapılandırma](../../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)