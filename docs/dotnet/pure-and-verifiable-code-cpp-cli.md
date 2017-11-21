---
title: "Saf ve doğrulanabilen kod (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /clr compiler option [C++], verifiable assemblies
- /clr compiler option [C++], mixed assemblies
- pure MSIL [C++]
- verifiable assemblies [C++]
- verifiably type-safe code [C++]
- /clr compiler option [C++], pure assemblies
- .NET Framework [C++], pure and verifiable code
- assemblies [C++], mixed code
- verifiable assemblies [C++], about verifiable assemblies
- mixed assemblies [C++], about mixed assemblies
- pure MSIL [C++], about pure code
- assemblies [C++], verifiable code
- mixed assemblies [C++]
- assemblies [C++], pure code
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
caps.latest.revision: "31"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9ec68a6179cd74020638aa895028942bc76e21f5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="pure-and-verifiable-code-ccli"></a>Saf ve Doğrulanabilen Kod (C++/CLI)
.NET programlama için Visual C++ birbirinden farklı üç bileşenleri ve uygulamaları oluşturmayı destekler: karışık, saf ve doğrulanabilen. Üç aracılığıyla kullanılabilir [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği.  
  
## <a name="remarks"></a>Açıklamalar  
 Doğrulanabilen derlemeler hakkında daha fazla bilgi için bkz:  
  
-   [Karışık, saf ve doğrulanabilen özellik karşılaştırması (C + +/ CLI)](../dotnet/mixed-pure-and-verifiable-feature-comparison-cpp-cli.md)  
  
-   [Nasıl yapılır: pure'a Geçiş: Saf (C + +/ CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [Nasıl yapılır: doğrulanabilir C++ projeleri oluşturma (C + +/ CLI)](../dotnet/how-to-create-verifiable-cpp-projects-cpp-cli.md)  
  
-   [Nasıl yapılır: safe'e geçiş (C + +/ CLI)](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)  
  
-   [SQL Server ile doğrulanabilen derlemeler kullanma (C + +/ CLI)](../dotnet/using-verifiable-assemblies-with-sql-server-cpp-cli.md)  
  
-   [En iyi güvenlik uygulamaları](../security/security-best-practices-for-cpp.md)  
  
-   [Projeleri karışık moddan saf Ara dile dönüştürme](../dotnet/converting-projects-from-mixed-mode-to-pure-intermediate-language.md)  
  
## <a name="mixed-clr"></a>Karma (/ clr)  
 Karışık derlemeler (ile derlenmiş **/CLR**), hem de yönetilmeyen içerir ve yönetilen bölümleri, bunlar için .NET özellikleri kullanmak olası hale getirerek hala ancak yönetilmeyen kod içerir. Bu, tüm proje yazılması gerekmeden .NET özellikleri kullanmak uygulamaları ve bileşenleri güncelleştirilmesini sağlar. Visual C++ yönetilen ve yönetilmeyen kodu bu şekilde karıştırmak kullanmayı C++ birlikte çalışabilirliği adı verilir. Daha fazla bilgi için bkz: [karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md) ve [yerel ve .NET birlikte çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md).  
  
## <a name="pure-clrpure"></a>Saf (/ clr: pure)  
 Saf derlemeler (ile derlenmiş **/CLR: pure**) hem de yerel ve yönetilen veri türleri içerebilir, ancak yalnızca yönetilen işlevler. Karışık derlemeler gibi saf derlemeler P/Invoke aracılığıyla yerel DLL'leri ile birlikte çalışabilirlik izin ver (bkz [kullanma (DllImport özniteliği) C++'ta açık PInvoke](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)), ancak C++ birlikte çalışabilirlik özellikleri kullanılamaz. Ayrıca, saf derlemeler giriş noktaları saf derleme kullanımda olduğundan, yerel işlevlerden işlevleri verilemiyor [__clrcall](../cpp/clrcall.md) çağırma.  
  
### <a name="advantages-of-clrpure"></a>Avantajları/CLR: pure  
  
-   Daha iyi performans: Saf derlemeler yalnızca MSIL içerdiğinden, yerel işlevler vardır ve bu nedenle hiçbir yönetilen ve yönetilmeyen geçişler gereklidir. (P/Invoke yapılan işlev çağrıları bu kural için bir özel durumdur.)  
  
-   AppDomain Tanıma: İçinde yönetilen işlevler ve CLR Türleri mevcut `Application Domains`, kendi görünürlük ve erişilebilirlik etkiler. Saf derlemeler etki alanı algılayan (__declspec ([appdomain](../cpp/appdomain.md)) her tür için örtük), türleri ve işlevselliğini diğer .NET bileşenlerini erişme daha kolay ve güvenli şekilde. Sonuç olarak, saf derlemeler daha kolay karışık derlemeler kıyasla diğer .NET bileşenleriyle birlikte çalışmanız.  
  
-   Disksiz yükleme: bellek içi ve hatta akabilir saf derlemeler yüklenebilir. Bu, .NET derlemelerini depolanmış yordam olarak kullanmak için gereklidir. Bu, bağımlılık Windows nedeniyle yükleme mekanizmaları gerekir mevcut disk üzerinde yürütmek için karışık derlemelerden farklıdır.  
  
-   Yansıma: Saf derlemeler tam yansıtma desteği sağladığından, karma yürütülebilir dosyalar üzerinde yansıtacak şekilde mümkün değildir. Daha fazla bilgi için bkz: [yansıma (C + +/ CLI)](../dotnet/reflection-cpp-cli.md).  
  
-   Ana bilgisayar Denetlenebilirliği: Saf derlemeler yalnızca MSIL içerdiğinden daha tahmin edilebilir ve uygulamaları barındıran kullanıldığında derlemeleri CLR karışık ve varsayılan davranışını daha esnek davranırlar.  
  
### <a name="limitations-of-clrpure"></a>/ CLR sınırlamaları: Saf  
 Bu bölümde tarafından şu anda desteklenmeyen özellikleri kapsar **/CLR: pure**.  
  
-   Saf derlemeler yönetilmeyen işlevler tarafından çağrılamaz. Bu nedenle saf derlemeler COM arabirimlerini veya yerel geri çağırmalar. Saf derlemeler __declspec(dllexport) aracılığıyla işlevleri veremiyor veya. DEF dosyaları. Ayrıca, ile işlevler bildirilen \__clrcall kuralı aracılığıyla aktarılamıyor \__declspec(dllimport). Yerel bir modül işlevlerde saf derlemeden çağrılabilir, ancak işlevsellik saf derlemede gösterme karışık bir derlemedeki yönetilen işlevler aracılığıyla yapılmalıdır şekilde saf derlemeler yerel çağrılabilir işlevleri gösteremez. Bkz: [nasıl yapılır: pure'a Geçiş: Saf (C + +/ CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md) daha fazla bilgi için.  
  
-   ATL ve MFC kitaplıkları, Visual C++'ta saf mod derlemesi tarafından desteklenmez.  
  
-   Saf .netmodules kabul edilmez Visual C++ bağlayıcı girişi olarak. Ancak, saf .obj dosyaları bağlayıcı tarafından kabul edilir ve .obj dosyaları netmodule'ler içinde bulunan bilgileri kümesi içerir. Bkz: [bağlayıcı girişi olarak .netmodule dosyaları](../build/reference/netmodule-files-as-linker-input.md) daha fazla bilgi için.  
  
-   Bu yönetilmeyen talimatları saf derleme gösterebileceği gibi derleyici COM desteği (#import) desteklenmiyor.  
  
-   Kayan nokta hizalama ve özel durum işleme seçeneklerini saf derlemeler için ayarlanabilir değildir. Sonuç olarak, __declspec(align) kullanılamaz. Bu fpieee.h gibi bazı başlık dosyalarını/CLR ile uyumsuz işler: Saf.  
  
-   PSDK GetLastError işlevinde tanımsız davranış ile derleme yapılırken verebilirsiniz **/CLR: pure**.  
  
## <a name="verifiable-clrsafe"></a>Doğrulanabilen (/ CLR: safe)  
 **/CLR: safe** derleyici seçeneği Visual Basic ve C ortak dil çalışma zamanı (CLR) kodu değil ihlal güvence altına almak için geçerli izin gereksinimleri uyumsuz # yazılmış gelenler doğrulanabilen derlemeler oluşturur güvenlik ayarları. Örneğin, güvenlik ayarlarını diske yazılırken bir bileşen yasaklarsanız, CLR herhangi bir kodu çalıştırmadan önce doğrulanabilen bir bileşenin bu ölçütü karşılayıp karşılamadığını belirleyebilir. Doğrulanabilen derlemeler için CRT desteği yoktur. (CRT desteği saf derlemeler C çalışma zamanı kitaplığı saf MSIL sürümü aracılığıyla kullanılabilir.)  
  
 Doğrulanabilen derlemeler saf ve karışık derlemeler aşağıdaki avantajları sunar:  
  
-   Güvenliği artırmak.  
  
-   Bazı durumlarda, (örneğin, SQL bileşenleri) gerektirir.  
  
-   Windows'un gelecekteki sürümleri giderek bileşenleri ve uygulamaların doğrulanabilir olmasını gerektirir.  
  
 Bir dezavantajı, C++ birlikte çalışma özellikleri kullanılamaz ' dir. Yönetilen kod tarafından başvurulmayan olsa bile doğrulanabilen derlemeler herhangi bir yönetilmeyen işlevleri veya yerel veri türleri içeremez.  
  
 "Güvenli" sözcük kullanımı rağmen uygulamalarla derleme **/CLR: safe** gelmez hiçbir hatalar yoktur; yalnızca CLR çalışma zamanında güvenlik ayarlarını doğrulayabilirsiniz gösterir.  
  
 Derleme türünden bağımsız olarak yönetilen derlemelerden Yerel DLL'leri P/Invoke aracılığıyla yapılan çağrılar derlenir ancak güvenlik ayarlarına bağlı olarak çalışma zamanında başarısız olabilir.  
  
> [!NOTE]
>  Derleyiciyi geçecek ancak doğrulanamayan bir derlemede sonuçlanacak bir kodlama senaryo vardır: kapsam çözümü işleci kullanarak bir nesne örneği aracılığıyla sanal bir işlevi çağırmak.  Örneğin: `MyObj -> A::VirtualFunction();`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)