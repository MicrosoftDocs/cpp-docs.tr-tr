---
title: Masaüstü uygulamaları (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: a020b534-293c-44e2-aa48-516c43ddeb8f
caps.latest.revision: 17
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 61f52dead8ca7ecad52b1cef4f1d87ffc5830386
ms.sourcegitcommit: 78e5e5cdbafd29e2a6ccf68d4cce215136952907
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2018
---
# <a name="desktop-applications-visual-c"></a>Masaüstü uygulamaları (Visual C++)
A *masaüstü uygulaması* c++'ta Windows API'ları ve penceresinde veya sistem konsolu ya da çalışır, tamamını erişmek için yerel bir uygulamadır. Masaüstü uygulamalarında C++ (Windows XP artık resmi olarak desteklenir ve o zamandan bu yana sunulan çok sayıda Windows API'leri vardır rağmen), Windows XP ile Windows 10 çalıştırabilirsiniz.   Bir masaüstü uygulaması Windows 10 çalıştıran bilgisayarlarda ve aynı zamanda XBox, Windows Phone, Surface Hub ve diğer aygıtlar üzerinde çalıştırılabilir bir evrensel Windows Platformu (UWP) uygulamasını farklıdır. Masaüstü vs hakkında daha fazla bilgi için. UWP uygulamalar için bkz [teknolojiyi seçin](https://msdn.microsoft.com/en-us/library/windows/desktop/dn614993\(v=vs.85\).aspx).  
  
 **Terminolojisi**  
  
-   A *Win32* uygulamasıdır yapabilirsiniz c++ masaüstü uygulaması kullanmak yerel bir Windows [Windows C API'lerini ve/veya COM API'leri](https://msdn.microsoft.com/en-us/library/windows/desktop/ff818516\(v=vs.85\).aspx) CRT ve standart kitaplığı API'leri ve 3 taraf kitaplıklar. Bir pencerede çalıştıran bir Win32 uygulaması Windows iletilerin bir Windows yordamı işlevi içinde açıkça çalışmak Geliştirici gerektirir. Ad rağmen 32-bit (x86) veya 64-bit (x64) ikili olarak bir Win32 uygulaması derlenebilir. Visual Studio IDE'de Win32 ve şartları x86 eşanlamlıdır.  
  
-   [Bileşen Nesne Modeli (COM)](https://msdn.microsoft.com/en-us/library/windows/desktop/ms694363\(v=vs.85\).aspx) , birbirleriyle iletişim kurmak için farklı dillerde yazılmış programları sağlayan bir özelliğidir. Çok sayıda Windows bileşenleri COM nesneleri olarak uygulanır ve standart COM Nesne oluşturma kurallarına bulma ve nesne yok etme arabirim.  COM nesneleri C++ Masaüstü uygulamalardan kullanarak oldukça basittir ancak kendi COM nesnesi yazma daha gelişmiş. [Etkin Şablon kitaplığı (ATL)](../atl/atl-com-desktop-components.md) makroları ve COM Geliştirme basitleştirmeye yardımcı işlevleri sağlar.  
  
-   MFC uygulaması kullanan bir Windows Masaüstü uygulamasıdır [Microsoft Foundation sınıfları](../mfc/mfc-desktop-applications.md) kullanıcı arabirimini oluşturmak için. MFC uygulaması COM bileşenlerini yanı sıra CRT ve standart kitaplığı API de kullanabilirsiniz. MFC pencere ileti döngüsü ve Windows API'leri üzerinden nesne odaklı basit bir C++ kapsayıcı sağlar. MFC uygulamaları için varsayılan seçimdir — özellikle Kurumsal türü uygulamaları — çok sayıda kullanıcı arabirimi denetimlerini veya özel kullanıcı denetimleri vardır. MFC pencere yönetimi, seri hale getirme, metin düzenleme, yazdırma ve Şerit gibi modern kullanıcı arabirimi öğeleri için kullanışlı yardımcı sınıfları sağlar. MFC ile etkili olması için Win32 ile tanımanız gerekir.  
  
-   C + +/ CLI uygulamanın veya bileşenin C++ söz dizimini Uzantıları (C++ belirtimine göre izin verilen gibi) .NET ve yerel C ++ kodu arasındaki etkileşimi etkinleştirmek için kullanır.  C + +/ CLI uygulama yerel olarak çalıştır bölümleri ve .NET temel sınıf kitaplığı'na erişimi olan .NET Framework çalışan bölümleri sahip olabilir. C + +/ CLI olduğunda tercih seçeneği C# veya Visual Basic ile yazılan kod ile çalışmak için gereken yerel C++ koduna sahip. .NET DLL'leri yerine kullanıcı arabirimi kodu kullanmak için öncelikle yöneliktir. Daha fazla bilgi için bkz: [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).  
  
 C++ Masaüstü herhangi bir uygulamada C çalışma zamanı (CRT) ve standart kitaplığı sınıfları ve İşlevler, COM nesneleri ve topluca Windows API bilinen ortak Windows işlevlerini kullanabilirsiniz. C++'ta Windows Masaüstü uygulamaları giriş için bkz: [c++ programı için Windows edinin](http://go.microsoft.com/fwlink/p/?LinkId=262281).  
  
## <a name="in-this-section"></a>Bu bölümde  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Konsol uygulamaları](../windows/console-applications-in-visual-cpp.md)|Konsol uygulamaları hakkında bilgiler içerir. Win32 (veya Win64) konsol uygulaması kendi pencere ve hiçbir ileti döngüsü vardır. Konsol penceresinde çalışır ve giriş ve çıkış komut satırı işlenir.|  
|[Windows Masaüstü uygulamaları](../windows/windows-desktop-applications-cpp.md)|Konsolun aksine Windows çalıştıran masaüstü uygulamalarının nasıl oluşturulacağını.|  
|[(C++) DirectX kullanarak oyun oluşturmak için kaynaklar](../windows/resources-for-creating-a-game-using-directx.md)|C++'ta oyun oluşturmak için içerik bağlantılar.|  
|[İzlenecek yol: Oluşturma ve bir statik kitaplık kullanma](../windows/walkthrough-creating-and-using-a-static-library-cpp.md)|.Lib ikili dosya oluşturma|  
|[Nasıl yapılır: Windows 10 SDK’yı bir Windows Masaüstü Uygulamasında Kullanma](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows 10 SDK'sını kullanarak oluşturmak projenizi adımlarını içerir.|  
  
## <a name="related-articles"></a>İlgili Makaleler  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Windows Geliştirme](http://go.microsoft.com/fwlink/p/?LinkId=262282)|Windows API ve COM hakkında bilgiler içerir (Bazı Windows API'ları ve üçüncü taraf DLL'leri COM nesneleri olarak uygulanır.)|  
|[Hilo: Windows 7 için C++ uygulamaları geliştirme](http://go.microsoft.com/fwlink/p/?LinkId=262284)|Karusel tabanlı kullanıcı arabirimi oluşturmak üzere Windows animasyon ve Direct2D kullanan bir zengin istemci Windows Masaüstü uygulamasının nasıl oluşturulacağını açıklar.  Bu öğretici Windows 7 bu yana güncelleştirilmemiş ancak hala Win32 programlama kapsamlı bir giriş sağlar.|  
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual Studio ve bağlantıları Visual C++ belge geri kalanı için Visual C++ anahtar özelliklerini açıklar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++](../visual-cpp-in-visual-studio.md)
