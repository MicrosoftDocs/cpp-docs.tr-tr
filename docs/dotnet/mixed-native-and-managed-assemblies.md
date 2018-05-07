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
ms.openlocfilehash: 0ac18841d5050bc8fb849ac542dc298ce89c964f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="mixed-native-and-managed-assemblies"></a>Karışık (Yerel ve Yönetilen) Derlemeler
Karışık derlemeler yönetilmeyen makine yönergeleri ve MSIL yönergeleri içeremeyeceğini. Bu arayın ve .NET bileşenleri tarafından tamamen yönetilmeyen bileşenleri ile uyumluluk korurken çağrılması sağlar. Karışık derlemeler kullanarak, geliştiriciler yönetilen ve yönetilmeyen işlevleri karışımını kullanan uygulamalar yazabilirsiniz. Bu karışık derlemeler mevcut Visual C++ uygulamaları geçirme .NET platformu için ideal hale getirir.  
  
 Örneğin, tamamen yönetilmeyen işlevlerden oluşan bir varolan uygulama için .NET platformu tek modülüyle derleyerek getirilebilir **/CLR** derleyici anahtar. Bu modül .NET özelliklerini kullanabilmek için, ancak uygulama geri kalanı ile uyumlu olarak kalır. Bu şekilde, bir uygulama bir aşamalı, parça tarafından parça şekilde .NET platformu dönüştürülebilir. Yönetilen ve yönetilmeyen derleme aynı dosya içerisinde işlevi tarafından işlevi temelinde arasında karar vermek bile mümkündür (bkz [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md)).  
  
 Visual C++ Yönetilen derlemeler üç farklı türde oluşturulmasını destekler: karışık, saf ve doğrulanabilen. İkinci iki ele alınmıştır [saf ve doğrulanabilen kod (C + +/ CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Nasıl yapılır: pure'a Geçiş](../dotnet/how-to-migrate-to-clr.md)  
 Giriş veya .NET işlevselliği, uygulamanızda yükseltme için önerilen adımları açıklar.  
  
 [Nasıl yapılır: / CLR MFC ve ATL kodu kullanarak derleme](../dotnet/how-to-compile-mfc-and-atl-code-by-using-clr.md)  
 Ortak dil çalışma zamanı hedeflemek için varolan MFC ve ATL programlarının nasıl yapılandırılabileceğini açıklar.  
  
 [Karışık Derlemeleri Başlatma](../dotnet/initialization-of-mixed-assemblies.md)  
 "Yükleyici kilidi" sorun ve çözümler açıklanmaktadır.  
  
 [Karışık Derlemeler için Kitaplık Desteği](../dotnet/library-support-for-mixed-assemblies.md)  
 Yerel kitaplıklarında nasıl anlatılmaktadır **/CLR** derlemeleri.  
  
 [Performans Konuları](../dotnet/performance-considerations-for-interop-cpp.md)  
 Karışık derlemeler ve verileri hazırlama performans etkilerini açıklar.  
  
 [Uygulama Etki Alanları ve Visual C++](../dotnet/application-domains-and-visual-cpp.md)  
 Uygulama etki alanları için Visual C++ desteğini açıklar.  
  
 [Çift dönüştürme](../dotnet/double-thunking-cpp.md)  
 Yönetilen bir işlev için yerel giriş noktası performans etkilerini açıklar.  
  
 [/ CLR ile CLR kapatma sırasında oluşturulan COM nesnelerini tüketirken özel durumları önleme](../dotnet/avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr.md)  
 İle derlenen bir COM nesnesi tüketen yönetilen bir uygulamanın düzgün kapatma emin olmak nasıl ele **/CLR**.  
  
 [Nasıl yapılır: CRT Kitaplık DLL'inden Bağımlılık Kaldırarak Kısmen Güvenilir Uygulama Oluşturma](../dotnet/create-a-partially-trusted-application.md)  
 Visual C++ kullanarak msvcm90.dll bağımlılık kaldırarak kısmen güvenilir bir ortak dil çalışma zamanı uygulamasının nasıl oluşturulacağını açıklar.  
  
 Karışık derlemeler için kodlama yönergeleri hakkında daha fazla bilgi için bkz: "Bir genel bakış, yönetilen/yönetilmeyen kod birlikte çalışabilirliği" MSDN makalesine [ http://msdn.microsoft.com/netframework/default.aspx?pull=/library/dndotnet/html/manunmancode.asp ](http://msdn.microsoft.com/netframework/default.aspx?pull=/library/dndotnet/html/manunmancode.asp).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)