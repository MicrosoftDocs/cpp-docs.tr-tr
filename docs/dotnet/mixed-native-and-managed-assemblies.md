---
title: Karışık (yerel ve yönetilen) derlemeler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], mixed assemblies
- /clr compiler option [C++], mixed assemblies
- managed code [C++], interoperability
- interoperability [C++], mixed assemblies
- mixed DLL loading [C++]
- mixed assemblies [C++], about mixed assemblies
- assemblies [C++], mixed
- mixed assemblies [C++]
- native code [C++], .NET interoperatibility
ms.assetid: 4299dfce-392f-4933-8bf0-5da2f0d1c282
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 469e0429408e1b8afed65889539202650cd28413
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704795"
---
# <a name="mixed-native-and-managed-assemblies"></a>Karışık (yerel ve yönetilen) derlemeler

Karışık derlemeler yönetilmeyen makine yönergeleri ve MSIL yönergeleri içeremeyeceğini. Bu arayın ve .NET bileşenleri tarafından tamamen yönetilmeyen bileşenleri ile uyumluluk korurken çağrılması sağlar. Karışık derlemeler kullanarak, geliştiriciler yönetilen ve yönetilmeyen işlevleri karışımını kullanan uygulamalar yazabilirsiniz. Bu karışık derlemeler mevcut Visual C++ uygulamaları geçirme .NET platformu için ideal hale getirir.

Örneğin, tamamen yönetilmeyen işlevlerden oluşan bir varolan uygulama için .NET platformu tek modülüyle derleyerek getirilebilir **/CLR** derleyici anahtar. Bu modül .NET özelliklerini kullanabilmek için, ancak uygulama geri kalanı ile uyumlu olarak kalır. Bu şekilde, bir uygulama bir aşamalı, parça tarafından parça şekilde .NET platformu dönüştürülebilir. Yönetilen ve yönetilmeyen derleme aynı dosya içerisinde işlevi tarafından işlevi temelinde arasında karar vermek bile mümkündür (bkz [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md)).

Visual C++ yalnızca kullanarak karışık Yönetilen derlemeler oluşturulmasını destekler **/CLR** derleyici seçeneği. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor. Saf veya doğrulanabilen Yönetilen derlemeler gerekiyorsa, bunları C# kullanarak oluşturmanız önerilir.

Visual C++ Derleyici araç setini önceki sürümlerinde desteklenen birbirinden farklı üç Yönetilen derlemeler oluşturma: karışık, saf ve doğrulanabilen. İkinci iki ele alınmıştır [saf ve doğrulanabilen kod (C + +/ CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md).

## <a name="in-this-section"></a>Bu bölümde

[Nasıl yapılır: pure'a Geçiş](../dotnet/how-to-migrate-to-clr.md)<br/>
Giriş veya .NET işlevselliği, uygulamanızda yükseltme için önerilen adımları açıklar.

[Nasıl yapılır: / CLR MFC ve ATL kodu kullanarak derleme](../dotnet/how-to-compile-mfc-and-atl-code-by-using-clr.md)<br/>
Ortak dil çalışma zamanı hedeflemek için varolan MFC ve ATL programlarının nasıl yapılandırılabileceğini açıklar.

[Karışık Derlemeleri Başlatma](../dotnet/initialization-of-mixed-assemblies.md)<br/>
"Yükleyici kilidi" sorun ve çözümler açıklanmaktadır.

[Karışık Derlemeler için Kitaplık Desteği](../dotnet/library-support-for-mixed-assemblies.md)<br/>
Yerel kitaplıklarında nasıl anlatılmaktadır **/CLR** derlemeleri.

[Performans Konuları](../dotnet/performance-considerations-for-interop-cpp.md)<br/>
Karışık derlemeler ve verileri hazırlama performans etkilerini açıklar.

[Uygulama Etki Alanları ve Visual C++](../dotnet/application-domains-and-visual-cpp.md)<br/>
Uygulama etki alanları için Visual C++ desteğini açıklar.

[Çift dönüştürme](../dotnet/double-thunking-cpp.md)<br/>
Yönetilen bir işlev için yerel giriş noktası performans etkilerini açıklar.

[/ CLR ile CLR kapatma sırasında oluşturulan COM nesnelerini tüketirken özel durumları önleme](../dotnet/avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr.md)<br/>
İle derlenen bir COM nesnesi tüketen yönetilen bir uygulamanın düzgün kapatma emin olmak nasıl ele **/CLR**.

[Nasıl yapılır: CRT Kitaplık DLL'inden Bağımlılık Kaldırarak Kısmen Güvenilir Uygulama Oluşturma](../dotnet/create-a-partially-trusted-application.md)<br/>
Visual C++ kullanarak msvcm90.dll bağımlılık kaldırarak kısmen güvenilir bir ortak dil çalışma zamanı uygulamasının nasıl oluşturulacağını açıklar.

Karışık derlemeler için kodlama yönergeleri hakkında daha fazla bilgi için MSDN makalesine bakın [bir genel bakış, yönetilen/yönetilmeyen kod birlikte çalışabilirliği](https://msdn.microsoft.com/en-us/library/ms973872.aspx).

## <a name="see-also"></a>Ayrıca bkz.

- [Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)
