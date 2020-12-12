---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3505'
title: Derleyici hatası C3505
ms.date: 11/04/2016
f1_keywords:
- C3505
helpviewer_keywords:
- C3505
ms.assetid: ed73c99e-93a1-4f3a-bac7-ba7ed5d836e4
ms.openlocfilehash: 10727b04ce587eb56872440ad7d46dd544eb0642
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113134"
---
# <a name="compiler-error-c3505"></a>Derleyici hatası C3505

> '*Guid*' tür kitaplığı yüklenemiyor

C3505, bir 64-bit makinede 64 bit, x86-barındırılan platformlar arası çapraz derleyicisini 32 çalıştırıyorsanız, derleyici WOW64 altında çalıştığından ve yalnızca 32-bit kayıt defteri kovanına okuyabildiğinden oluşabilir.

Bu hatayı, içeri aktarmaya çalıştığınız tür kitaplığının hem 32-bit hem de 64-bit sürümlerini oluşturarak çözümleyebilir ve bunları her ikisi de kaydedebilirsiniz.  Ya da yerel 64 bit derleyicisini kullanarak, IDE 'deki **VC + + dizinleri** özelliğini 64 bit derleyicisini işaret etmek için değiştirmeniz gerekir.

Daha fazla bilgi için bkz.,

- [Nasıl yapılır: Komut Satırında 64 Bit Visual C++ Araç Takımını Etkinleştirme](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)

- [Nasıl Yapılır: Visual C++ Projelerinin 64 Bit, x64 Platformları Hedeflemesi için Yapılandırma](../../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)
