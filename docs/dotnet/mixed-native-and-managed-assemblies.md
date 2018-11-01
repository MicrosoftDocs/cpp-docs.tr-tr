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
ms.openlocfilehash: 78e95177282804369bac2065582a06b8acbc975b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428693"
---
# <a name="mixed-native-and-managed-assemblies"></a>Karışık (yerel ve yönetilen) derlemeler

Karışık derlemeler yönetilmeyen makine yönergelerine hem MSIL yönergeleri içeren özelliğine sahiptir. Bu çağrı ve yerel C++ kitaplıkları ile uyumluluğu korurken .NET bileşenleri tarafından çağrılmak sağlar. Karışık derlemeler kullanarak, geliştiricilerin .NET ve yerel C++ kodunu bir karışımını kullanan uygulamalar yazabilirsiniz.

Örneğin, tamamen yerel C++ kodunu içeren mevcut bir kitaplık .NET platformu için bir modülün ile derleyerek getirilebilir **/CLR** derleyici anahtarı. Bu modül, .NET özelliklerini kullanabilmek için ise, ancak uygulama geri kalanı ile uyumlu kalır. Yönetilen ve yerel derleme işlevi tarafından işlevi olarak aynı dosya içerisinde arasında karar vermek bile mümkündür (bkz [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md)).

Visual C++ yalnızca kullanarak karışık Yönetilen derlemeler oluşturulmasını destekler **/CLR** derleyici seçeneği. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor. Saf veya doğrulanabilir Yönetilen derlemeler gerekiyorsa, bunları C# kullanarak oluşturmanız önerilir.

Visual C++ Derleyici Araç Takımı'nın önceki sürümlerinde desteklenen yönetilen derlemeleri birbirinden farklı üç nesil: karışık, saf ve doğrulanabilen. İkinci iki ele alınmıştır [saf ve doğrulanabilen kod (C + +/ CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md).

## <a name="in-this-section"></a>Bu bölümde

[Nasıl yapılır: / CLR'ye geçiş](../dotnet/how-to-migrate-to-clr.md)<br/>
Karşınızda veya uygulamanız .NET işlevselliği yükseltme için önerilen adımlar açıklanır.

[Nasıl yapılır: derleme MFC ve ATL kodu kullanarak/CLR](../dotnet/how-to-compile-mfc-and-atl-code-by-using-clr.md)<br/>
Ortak dil çalışma zamanını hedeflemek için mevcut MFC ve ATL programlarının nasıl yapılandırılabileceğini açıklar.

[Karışık Derlemeleri Başlatma](../dotnet/initialization-of-mixed-assemblies.md)<br/>
"Yükleyici kilidi" sorun ve çözümler açıklanmaktadır.

[Karışık Derlemeler için Kitaplık Desteği](../dotnet/library-support-for-mixed-assemblies.md)<br/>
Yerel kitaplıkları kullanma açıklanır **/CLR** derlemeleri.

[Performans Konuları](../dotnet/performance-considerations-for-interop-cpp.md)<br/>
Karışık derlemeler ve verileri hazırlama performans etkilerini açıklar.

[Uygulama Etki Alanları ve Visual C++](../dotnet/application-domains-and-visual-cpp.md)<br/>
Uygulama etki alanları için Visual C++ desteği açıklanmaktadır.

[Çift dönüştürme](../dotnet/double-thunking-cpp.md)<br/>
Yönetilen bir işlev için bir yerel giriş noktasının performans etkileri anlatılmaktadır.

[/ CLR ile CLR kapatma sırasında oluşturulan COM nesnelerini tüketirken özel durumları önleme](../dotnet/avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr.md)<br/>
Bir COM nesnesi ile derlenmiş tüketen yönetilen bir uygulamanın düzgün kapatma emin olmak nasıl ele alınmaktadır **/CLR**.

[Nasıl yapılır: CRT Kitaplık DLL'inden Bağımlılık Kaldırarak Kısmen Güvenilir Uygulama Oluşturma](../dotnet/create-a-partially-trusted-application.md)<br/>
Visual C++ msvcm90.dll bağımlılık kaldırarak kullanarak kısmen güvenilir bir ortak dil çalışma zamanı uygulamasının nasıl oluşturulacağını açıklar.

Karışık derlemeler için kodlama yönergeleri hakkında daha fazla bilgi için bkz MSDN makalesine [bir genel bakış, yönetilen/yönetilmeyen kod birlikte çalışabilirliği](https://msdn.microsoft.com/library/ms973872.aspx).

## <a name="see-also"></a>Ayrıca bkz.

- [Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)
