---
title: "Karışık derlemeler için kitaplık desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- msvcm90[d].dll
- mixed assemblies [C++], library support
- msvcmrt[d].lib
- libraries [C++], mixed assemblies
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9b3bc50416eceac64c134a31a4d7384e33db69b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="library-support-for-mixed-assemblies"></a>Karışık Derlemeler için Kitaplık Desteği
C++ Standart Kitaplığı, ortak çalışma zamanı kitaplığı (CRT) kullanılmasını destekler Visual C++ ATL ve MFC ile derlenmiş uygulamalar için [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md). Bu, .NET Framework özelliklerini kullanmak için bu kitaplıkları kullanan mevcut uygulamaları sağlar.  
  
 Bu destek, aşağıdaki yeni DLL ve içeri aktarma kitaplıkları sunar:  
  
-   / CLR ile derleme yaparsanız Msvcmrt [d] .lib. Karışık derlemeler bu içeri aktarma kitaplığını bağlanır.  
  
-   Msvcm90 [d] .dll ve/CLR ile derleme yaparsanız Msvcurt [d] .lib: Saf. DLL yönetilen C çalıştırma zamanı (CRT) desteği sağlama karışık bir derleme ve yönetilen bir derlemeyi genel derleme önbelleğinde (GAC) yüklü bir parçasıdır. Saf derlemeler bağlantısını bu içeri aktarma kitaplığı ve son Msvcm90.dll bağlanır.  
  
 Bu destek, ilgili bir kaç yarar sağlar:  
  
-   CRT ve C++ Standart Kitaplığı, karışık ve saf kod için kullanılabilir. CRT ve sağlanan C++ Standart Kitaplığı doğrulanabilir değildir; Sonuç olarak, yerel koddan kullanırken çağrılarınızı hala aynı CRT ve C++ Standart Kitaplığı yönlendirilir.  
  
-   Saf ve karışık görüntülerdeki birleşik özel durum işleme düzeltin.  
  
-   Saf ve karışık görüntülerdeki C++ değişkenlerinin statik başlatma.  
  
-   AppDomain başına ve işlem başına değişkenleri yönetilen kod desteği.  
  
-   Visual Studio 2003 ve önceki sürümlerinde derlenmiş Karışık DLL'ler uygulanan yükleyici kilidi sorunlarını giderir.  
  
 Ayrıca, aşağıdaki sınırlamalar Bu destek sunar:  
  
-   Yalnızca CRT DLL modeli desteklenir (her ikisi için/CLR veya/CLR ile derlenmiş kod: Saf).  
  
-   Bu nesneler, Visual C++ kitaplıkları kullanıyorsanız (tüm nesneleri saf bir görüntüde saf olması gerektiğinden) tek bir görüntüde saf ve karışık nesneleri karıştıramazsınız. Bunu yaparsanız, bağlantı zamanı hataları alırsınız.  
  
 Önceki sürümleri ile çalışması için kesin değildir gibi ortak dil çalışma zamanı (CLR) geçerli sürüme güncelleştirmeniz gerekir. Bu değişikliklerle oluşturulmuş kod CLR sürümü çalışmayacak 1.x.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)