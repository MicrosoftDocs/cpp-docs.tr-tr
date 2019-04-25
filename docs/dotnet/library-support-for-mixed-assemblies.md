---
title: Karışık Derlemeler için Kitaplık Desteği
ms.date: 09/18/2018
helpviewer_keywords:
- msvcm90[d].dll
- mixed assemblies [C++], library support
- msvcmrt[d].lib
- libraries [C++], mixed assemblies
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
ms.openlocfilehash: 42116c09d5b31cf669eb6d5d1e75eae60b2610a7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62312014"
---
# <a name="library-support-for-mixed-assemblies"></a>Karışık Derlemeler için Kitaplık Desteği

Visual C++, C++ Standart Kitaplığı, C çalışma zamanı kitaplığı (CRT) kullanılmasını destekler ATL ve MFC ile derlenmiş uygulamalar için [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md). Bu, .NET Framework özellikleri kullanmak için bu kitaplıkları kullanan mevcut uygulamaları sağlar.

> [!IMPORTANT]
> **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Bu destek aşağıdaki DLL ve içeri aktarma kitaplıklarını içerir:

- Derleme yaparsanız Msvcmrt [d] .lib **/CLR**. Karışık derlemeler bağlantısı bu içeri aktarma kitaplığı.

Bu destek, birkaç ilgili avantajları sağlar:

- C++ Standart Kitaplığı ve CRT karma kod için kullanılabilir. CRT ve C++ Standart Kitaplığı sağlanan doğrulanabilir değildir; Sonuç olarak, yerel koddan kullanıyorsanız çağrılarınızı hala aynı CRT ve C++ Standart Kitaplığı yönlendirilir.

- Birleştirilmiş bir özel durum işleme karma resimlerdeki düzeltin.

- Karma görüntüleri içindeki C++ değişkenlerin statik başlatma.

- Yönetilen kodda AppDomain başına ve işlem başına değişkenleri için destek.

- Visual Studio 2003 ve önceki sürümlerinde derlenmiş olan karma DLL'ler uygulanan yükleyici kilidi sorunlarını giderir.

Ayrıca, aşağıdaki sınırlamalar Bu destek sunar:

- CRT DLL modeli ile derlenen kod için desteklenen **/CLR**. Destek statik CRT kitaplık yok **/CLR** oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

- [Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)
