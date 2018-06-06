---
title: Karışık derlemeler için kitaplık desteği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- msvcm90[d].dll
- mixed assemblies [C++], library support
- msvcmrt[d].lib
- libraries [C++], mixed assemblies
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d4b584e0bacb1cb93cad33efdff807bb5fa9c8e2
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704117"
---
# <a name="library-support-for-mixed-assemblies"></a>Karışık Derlemeler için Kitaplık Desteği

C++ Standart Kitaplığı, C çalışma zamanı kitaplığı (CRT) kullanılmasını destekler Visual C++ ATL ve MFC ile derlenmiş uygulamalar için [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md). Bu, .NET Framework özelliklerini kullanmak için bu kitaplıkları kullanan mevcut uygulamaları sağlar.

> [!IMPORTANT]
> **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

Bu destek, aşağıdaki DLL ve içeri aktarma kitaplıkları içerir:

- İle derleme yaparsanız Msvcmrt [d] .lib **/CLR**. Bu içeri aktarma kitaplığını karışık derlemeler bağlantısı.

Bu destek, ilgili bir kaç yarar sağlar:

- CRT ve C++ Standart Kitaplığı karışık kod için kullanılabilir. CRT ve sağlanan C++ Standart Kitaplığı doğrulanabilir değildir; Sonuç olarak, yerel koddan kullanırken çağrılarınızı hala aynı CRT ve C++ Standart Kitaplığı yönlendirilir.

- Birleşik özel durum işleme karma görüntülerinde düzeltin.

- Statik başlatma C++ değişkenlerinin karma görüntüler.

- AppDomain başına ve işlem başına değişkenleri yönetilen kod desteği.

- Visual Studio 2003 ve önceki sürümlerinde derlenmiş Karışık DLL'ler uygulanan yükleyici kilidi sorunlarını giderir.

Ayrıca, aşağıdaki sınırlamalar Bu destek sunar:

- İle derlenmiş kod yalnızca CRT DLL modeli desteklenir **/CLR**. Destek statik CRT kitaplık yok **/CLR** oluşturur.

Önceki sürümleri ile çalışması için kesin değildir gibi ortak dil çalışma zamanı (CLR) geçerli sürüme güncelleştirmeniz gerekir. Bu değişikliklerle oluşturulmuş kod CLR sürümü çalışmayacak 1.x.

## <a name="see-also"></a>Ayrıca bkz.

- [Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)
