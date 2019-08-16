---
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
ms.openlocfilehash: 11bdfc98c64b2612129e10c002c68ee243bec7da
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501139"
---
# <a name="mixed-native-and-managed-assemblies"></a>Karışık (yerel ve yönetilen) derlemeler

Karışık derlemeler hem yönetilmeyen makine yönergelerini hem de MSIL yönergelerini içerir. Bu, yerel C++ kitaplıklarla uyumluluğu korurken .NET bileşenleri tarafından çağrılıp çağrılmalarını sağlar. Geliştiriciler, karışık derlemeler kullanarak .NET ve yerel C++ kod karışımını kullanarak uygulamalar yazabilir.

Örneğin, tamamen yerel C++ koddan oluşan mevcut bir kitaplık, **/clr** derleyici anahtarıyla yalnızca bir modül yeniden derlenerek .net platformuna getirilebilir. Bu modül daha sonra .NET özelliklerini kullanabilir, ancak uygulamanın geri kalanı ile uyumlu kalır. Aynı dosya içinde işlev olarak işlev temelinde yönetilen ve yerel derleme arasında seçim yapmak bile olasıdır (bkz. [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md)).

Görsel C++ yalnızca **/clr** derleyici seçeneği kullanılarak karışık yönetilen derlemelerin oluşturulmasını destekler. **/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez. Saf veya doğrulanabilir yönetilen derlemelere ihtiyaç duyuyorsanız, kullanarak C#bunları oluşturmanızı öneririz.

Microsoft C++ derleyicisi araç takımının önceki sürümleri, üç farklı türde yönetilen derlemenin oluşturulmasını destekliyordu: karışık, saf ve doğrulanabilir. İkinci iki, [saf ve Doğrulanabilen kodC++(/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)içinde ele alınmıştır.

## <a name="in-this-section"></a>Bu bölümde

[Nasıl yapılır: /Clr 'e geçiş](../dotnet/how-to-migrate-to-clr.md)<br/>
Uygulamanızda .NET işlevselliğini tanıtmak veya yükseltmek için önerilen adımları açıklar.

[Nasıl yapılır: /Clr kullanarak MFC ve ATL kodu derleme](../dotnet/how-to-compile-mfc-and-atl-code-by-using-clr.md)<br/>
Ortak dil çalışma zamanını hedeflemek için mevcut MFC ve ATL programlarının nasıl derleneceği açıklanır.

[Karışık Derlemeleri Başlatma](../dotnet/initialization-of-mixed-assemblies.md)<br/>
"Yükleyici kilidi" sorununu ve çözümlerini açıklar.

[Karışık Derlemeler için Kitaplık Desteği](../dotnet/library-support-for-mixed-assemblies.md)<br/>
**/Clr** derlemelerinde yerel kitaplıkların nasıl kullanılacağını açıklar.

[Performans Konuları](../dotnet/performance-considerations-for-interop-cpp.md)<br/>
Karma derlemelerin ve veri hazırlama performansının etkilerini açıklar.

[Uygulama Etki Alanları ve Visual C++](../dotnet/application-domains-and-visual-cpp.md)<br/>
Uygulama etki C++ alanları için görsel desteği açıklar.

[Çift dönüştürme](../dotnet/double-thunking-cpp.md)<br/>
Yönetilen işlev için yerel bir giriş noktasının performans etkilerini açıklar.

[/Clr ile oluşturulan COM nesnelerini tüketirken CLR kapatmasıyla ilgili özel durumları önleme](../dotnet/avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr.md)<br/>
**/Clr**ile derlenen bir com nesnesini kullanan yönetilen bir uygulamanın düzgün şekilde kapatılmasını nasıl sağlamak istediğinizi açıklar.

[Nasıl yapılır: CRT Kitaplık DLL'sinden Bağımlılığı Kaldırarak Kısmen Güvenilir Uygulama Oluşturma](../dotnet/create-a-partially-trusted-application.md)<br/>
Msvcm90. dll ' ye bağımlılığı kaldırarak, Visual C++ kullanılarak kısmen güvenilir bir ortak dil çalışma zamanı uygulamasının nasıl oluşturulduğunu açıklar.

Karışık derlemeler için kodlama yönergeleri hakkında daha fazla bilgi için bkz. MSDN makalesine [yönetilen/yönetilmeyen kod birlikte çalışabilirliğine genel bakış](/previous-versions/dotnet/articles/ms973872(v=msdn.10)).

## <a name="see-also"></a>Ayrıca bkz.

- [Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)
