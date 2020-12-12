---
description: 'Daha fazla bilgi edinin: karışık derlemeler için kitaplık desteği'
title: Karışık Derlemeler için Kitaplık Desteği
ms.date: 09/18/2018
helpviewer_keywords:
- msvcm90[d].dll
- mixed assemblies [C++], library support
- msvcmrt[d].lib
- libraries [C++], mixed assemblies
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
ms.openlocfilehash: d20069c2caa1cf46ebdb54907de586630d4ee71c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113720"
---
# <a name="library-support-for-mixed-assemblies"></a>Karışık Derlemeler için Kitaplık Desteği

Visual C++, [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)ile derlenen uygulamalar Için C++ standart kitaplığı, C çalışma zamanı KITAPLıĞı (CRT), ATL ve MFC kullanımını destekler. Bu, bu kitaplıkları kullanan mevcut uygulamaların de .NET Framework özellikleri kullanmasını sağlar.

> [!IMPORTANT]
> **/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

Bu destek, aşağıdaki DLL ve içeri aktarma kitaplıklarını içerir:

- **/Clr** ile derlerseniz msvcmrt [d]. lib. Bu içeri aktarma kitaplığına yönelik karışık derlemeler bağlantısı.

Bu destek, bazı ilgili avantajları sağlar:

- CRT ve C++ standart kitaplığı karışık kod ile kullanılabilir. Belirtilen CRT ve C++ standart kitaplığı doğrulanabilir değil; Sonuç olarak, çağrılarınız halen yerel koddan kullandığınız CRT ve C++ standart kitaplığına yönlendirilir.

- Karma görüntülerde Birleşik özel durum işlemeyi düzeltin.

- Karışık görüntülerde C++ değişkenlerinin statik başlatması.

- Yönetilen koddaki AppDomain başına ve işlem başına değişkenler için destek.

- Visual Studio 2003 ve önceki sürümlerde derlenen karışık dll 'lere uygulanan yükleyici kilit sorunlarını çözer.

Ayrıca, bu destek aşağıdaki sınırlamaları sunar:

- **/Clr** ile derlenen kod IÇIN yalnızca CRT DLL modeli desteklenir. **/Clr** derlemelerini destekleyen BIR statik CRT kitaplığı yok.

## <a name="see-also"></a>Ayrıca bkz.

- [Karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)
