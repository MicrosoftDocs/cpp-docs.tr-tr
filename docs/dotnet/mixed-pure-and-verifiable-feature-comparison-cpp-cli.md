---
title: "Karışık, saf ve doğrulanabilen özellik karşılaştırması (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- safe assemblies [C++], vs. pure
- mixed assemblies [C++], vs. pure
- safe assemblies [C++], vs. mixed
- pure MSIL [C++]
- verifiable assemblies [C++]
- pure MSIL [C++], vs. safe
- pure MSIL [C++], vs. mixed
- pure MSIL [C++], compared to mixed and safe
- verifiable assemblies [C++], vs. mixed
- mixed assemblies [C++], vs. safe
- verifiable assemblies [C++], vs. pure
- pure assemblies [C++]
- safe assemblies [C++]
- mixed assemblies [C++]
ms.assetid: 3f7a82ba-0e69-4927-ba0c-fbc3160e4394
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3ee9fbed3fd82fd450fd179683fd119cb1630034
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mixed-pure-and-verifiable-feature-comparison-ccli"></a>Karışık, Saf ve Doğrulanabilen Özellik Karşılaştırması (C++/CLI)
Bu konuda farklı arasında özellikleri karşılaştırılır **/CLR** derleme modları. Daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
## <a name="feature-comparison"></a>Özellik karşılaştırması  
  
|Özellik|Karma (/ clr)|Saf (/ clr: pure)|Güvenli (/ CLR: safe)|İlgili bilgiler|  
|-------------|---------------------|-------------------------|-------------------------|-------------------------|  
|CRT kitaplık|Desteklenen|Desteklenen||[Kategorilere Göre Çalışma Zamanı Yordamları](../c-runtime-library/run-time-routines-by-category.md)|  
|ATL/MFC|Desteklenen|||[MFC Masaüstü uygulamaları](../mfc/mfc-desktop-applications.md) &#124; [Sınıfı genel bakış](../atl/atl-class-overview.md)|  
|Yönetilmeyen İşlevler|Desteklenen|||[Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)|  
|Yönetilmeyen veri|Desteklenen|Desteklenen||[Saf ve Doğrulanabilen Kod (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)|  
|Yönetilmeyen işlevlerden çağrılabilir|Desteklenen|||[Nasıl yapılır: pure'a Geçiş: Saf (C + +/ CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)|  
|Yönetilmeyen işlevleri çağırma destekler|Desteklenen|Yalnızca C stili işlevleri|P/Invoke yalnızca|[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)|  
|Yansıma destekler|Sadece DLL'ler|Desteklenen|Desteklenen|[Yansıma (C++/CLI)](../dotnet/reflection-cpp-cli.md)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Saf ve Doğrulanabilen Kod (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)