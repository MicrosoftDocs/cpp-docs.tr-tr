---
description: 'Daha fazla bilgi edinin: karışık (yerel ve yönetilen) derlemeler'
title: Karışık (Yerel ve Yönetilen) Derlemeler
ms.date: 09/18/2018
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
ms.openlocfilehash: b96ccb5a521cf009f7feabef01a292ac805b0b4e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253660"
---
# <a name="mixed-native-and-managed-assemblies"></a>Karışık (yerel ve yönetilen) derlemeler

Karışık derlemeler hem yönetilmeyen makine yönergelerini hem de MSIL yönergelerini içerir. Bu, yerel C++ kitaplıklarıyla uyumluluğu korurken .NET bileşenleri tarafından çağrılıp çağrılmalarını sağlar. Geliştiriciler, karışık derlemeler kullanarak .NET ve yerel C++ kodu karışımını kullanarak uygulamalar yazabilir.

Örneğin, tamamen yerel C++ kodundan oluşan mevcut bir kitaplık, **/clr** derleyici anahtarıyla yalnızca bir modül yeniden derlenerek .net platformuna getirilebilir. Bu modül daha sonra .NET özelliklerini kullanabilir, ancak uygulamanın geri kalanı ile uyumlu kalır. Aynı dosya içinde işlev olarak işlev temelinde yönetilen ve yerel derleme arasında seçim yapmak bile olasıdır (bkz. [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md)).

Visual C++, yalnızca **/clr** derleyici seçeneği kullanılarak karışık yönetilen derlemelerin oluşturulmasını destekler. **/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez. Saf veya doğrulanabilir yönetilen derlemelere ihtiyacınız varsa, bunları C# kullanarak oluşturmanız önerilir.

Microsoft C++ derleyicisi araç takımının önceki sürümleri, üç farklı yönetilen derleme türü oluşturmayı destekliyordu: karışık, saf ve doğrulanabilir. İkinci iki, [saf ve Doğrulanabilen kod (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)içinde ele alınmıştır.

## <a name="in-this-section"></a>Bu bölümde

[Nasıl yapılır:/clr 'e geçiş](../dotnet/how-to-migrate-to-clr.md)<br/>
Uygulamanızda .NET işlevselliğini tanıtmak veya yükseltmek için önerilen adımları açıklar.

[Nasıl yapılır:/clr kullanarak MFC ve ATL kodu derleme](../dotnet/how-to-compile-mfc-and-atl-code-by-using-clr.md)<br/>
Ortak dil çalışma zamanını hedeflemek için mevcut MFC ve ATL programlarının nasıl derleneceği açıklanır.

[Karışık derlemeleri başlatma](../dotnet/initialization-of-mixed-assemblies.md)<br/>
"Yükleyici kilidi" sorununu ve çözümlerini açıklar.

[Karışık derlemeler için kitaplık desteği](../dotnet/library-support-for-mixed-assemblies.md)<br/>
**/Clr** derlemelerinde yerel kitaplıkların nasıl kullanılacağını açıklar.

[Performans konuları](../dotnet/performance-considerations-for-interop-cpp.md)<br/>
Karma derlemelerin ve veri hazırlama performansının etkilerini açıklar.

[Uygulama etki alanları ve Visual C++](../dotnet/application-domains-and-visual-cpp.md)<br/>
Uygulama etki alanları için Visual C++ desteğini açıklar.

[Çift dönüştürme](../dotnet/double-thunking-cpp.md)<br/>
Yönetilen işlev için yerel bir giriş noktasının performans etkilerini açıklar.

[/Clr ile oluşturulan COM nesnelerini tüketirken CLR kapatmasıyla ilgili özel durumları önleme](../dotnet/avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr.md)<br/>
**/Clr** ile derlenen bir com nesnesini kullanan yönetilen bir uygulamanın düzgün şekilde kapatılmasını nasıl sağlamak istediğinizi açıklar.

[Nasıl yapılır: CRT kitaplık DLL 'inin bağımlılığını kaldırarak kısmen güvenilen bir uygulama oluşturma](../dotnet/create-a-partially-trusted-application.md)<br/>
msvcm90.dll bağımlılığı kaldırılarak Visual C++ kullanılarak kısmen güvenilir bir ortak dil çalışma zamanı uygulamasının nasıl oluşturulduğunu açıklar.

Karışık derlemeler için kodlama yönergeleri hakkında daha fazla bilgi için bkz. [yönetilen/yönetilmeyen kod birlikte çalışabilirliğine genel bakış](/previous-versions/dotnet/articles/ms973872(v=msdn.10)).

## <a name="see-also"></a>Ayrıca bkz.

- [Yerel ve .NET birlikte çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)
