---
title: Masaüstü uygulamaları (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a020b534-293c-44e2-aa48-516c43ddeb8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9d4f44e3587e9b274bbe89e2fa4f91accadb08ab
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688265"
---
# <a name="desktop-applications-visual-c"></a>Masaüstü uygulamaları (Visual C++)

A *masaüstü uygulaması* c++'ta Windows API'leri ve ya da çalışan bir pencerede veya sistem konsolu tam kümesini erişebilmeniz için yerel bir uygulamadır. C++ Masaüstü uygulamaları, Windows XP ile Windows 10 (Windows XP artık resmi olarak desteklenir ve bu tarihten sonra sunulan çok sayıda Windows API vardır ancak) çalıştırabilirsiniz.

Windows 10 çalıştıran bilgisayarlara ve XBox, Windows Phone, Surface Hub ve diğer cihazlar üzerinde çalışabilen bir evrensel Windows Platformu (UWP) uygulamasını ayrı, bir masaüstü uygulamasıdır. Masaüstü vs hakkında daha fazla bilgi için. UWP uygulamaları [teknolojinizi seçin](https://msdn.microsoft.com/library/windows/desktop/dn614993\(v=vs.85\).aspx).


### <a name="desktop-bridge"></a>Masaüstü köprüsü

Windows 10'da mevcut masaüstü uygulamasını veya COM nesnesi bir UWP uygulaması olarak paketleme ve dokunma gibi UWP özellikleri ekleyebilir veya API'leri çağırmak modern Windows API kümesi. Visual Studio ve bunları tek bir birlikte paketlemek ve bunlar arasında iletişim kurmak için Windows API'leri kullanan paket masaüstü bir çözüme UWP uygulaması da ekleyebilirsiniz.

Visual Studio 2017 sürüm 15.4 ve daha sonra mevcut masaüstü uygulamanızı paketleme işini büyük ölçüde kolaylaştıran bir Windows uygulama paketi projesi oluşturabilirsiniz. Hangi kayıt defteri çağrıları ile ilgili bazı sınırlamalar veya Masaüstü uygulamanızı API'lerini kullanır, ancak çoğu durumda, bir uygulama paketi çalıştırılırken benzer işlevselliği elde etmek için başka bir kod yolları oluşturabilirsiniz. Daha fazla bilgi için [Masaüstü köprüsü](/windows-uwp/porting/desktop-to-uwp-root).

### <a name="terminology"></a>Terminoloji

- A *Win32* yapabileceğiniz c++ Masaüstü uygulamasını kullanın yerel bir Windows uygulamasıdır [Windows C API'leri ve/veya COM API'leri](https://msdn.microsoft.com/library/windows/desktop/ff818516\(v=vs.85\).aspx) CRT ve standart kitaplığı API'leri ve 3. taraf kitaplıkları. Bir pencere içinde çalışan bir Win32 uygulaması, Windows iletileri Windows yordamı işlevi içinde açıkça çalışmak Geliştirici gerektirir. Adını rağmen bir Win32 uygulaması bir 32-bit (x86) veya 64-bit (x64) ikili olarak derlenebilir. Visual Studio IDE'de x86 hüküm ve Win32 eşanlamlıdır.

- [Bileşen Nesne Modeli (COM)](/windows/desktop/com/the-component-object-model) birbirleriyle iletişim kurması için farklı dillerde yazılan programlar sağlayan bir özelliğidir. Bileşenleri COM nesneleri olarak uygulanır ve nesne oluşturma için standart COM kurallarına birçok Windows bulma ve nesne yok etme arabirim.  COM nesnelerinin C++ Masaüstü uygulamalarından kullanarak görece basittir, ancak kendi COM nesnesi yazmak daha gelişmiş. [Etkin Şablon kitaplığı (ATL)](../atl/atl-com-desktop-components.md) makroları ve COM geliştirmesini basitleştiren yardımcı işlevleri sağlar.

- Bir MFC uygulaması kullanan Windows masaüstü uygulaması olduğundan [Microsoft Foundation sınıfları](../mfc/mfc-desktop-applications.md) kullanıcı arabirimi oluşturmak için. Bir MFC uygulaması, COM bileşenlerinin yanı sıra CRT ve standart kitaplığı API'leri de kullanabilirsiniz. MFC pencere ileti döngüsü ve Windows API'ları üzerinde ince bir C++ nesne odaklı sarmalayıcı sağlar. MFC uygulamaları için varsayılan seçimdir — özellikle de kurumsal türde uygulamalar —, çok sayıda kullanıcı arabirimi denetimleri veya özel kullanıcı denetimi. MFC pencere yönetimi, serileştirme, metin yönetimi, yazdırma ve Şerit gibi modern kullanıcı arabirimi öğeleri için uygun yardımcı sınıflar sağlar. MFC ile etkili olması için Win32 ile ilgili bilgi sahibi olmanız gerekir.

- C + +/ CLI uygulama veya bileşen C++ sözdizimi uzantılarını (C++ belirtimi tarafından izin verilen gibi) .NET ve yerel C ++ kod arasındaki etkileşimi etkinleştirmek için kullanır.  C + +/ CLI uygulama yerel olarak çalıştırın parça ve .NET temel sınıf kitaplığı'na erişimi olan .NET Framework üzerinde bölümleri sahip olabilir. C + +/ CLI ile C# veya Visual Basic'te yazılmış kodun çalışması gereken yerel C++ kod varsa, tercih edilen seçeneği değildir. Ayrıca, .NET DLL'leri yerine kullanıcı arabirimi kodu kullanmak için öncelikle yöneliktir. Daha fazla bilgi için [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

Bir masaüstü uygulaması C++, C çalışma zamanı (CRT) ve standart kitaplığı sınıflarını ve işlevleri, COM nesnelerini ve topluca Windows API olarak bilinen ortak Windows işlevlerini kullanabilirsiniz. C++'ta Windows Masaüstü uygulamaları için bir giriş için bkz [programı için Windows c++ öğrenin](http://go.microsoft.com/fwlink/p/?LinkId=262281).

## <a name="in-this-section"></a>Bu bölümde

|Başlık|Açıklama|
|-----------|-----------------|
|[Konsol uygulamaları](../windows/console-applications-in-visual-cpp.md)|Konsol uygulamaları hakkında bilgi içerir. Bir Win32 (veya Win64) konsol uygulaması, kendi hiçbir penceresi ve ileti döngüsü vardır. Konsol penceresinde çalışır ve girdi ve çıktı komut satırı aracılığıyla işlenir.|
|[Windows Masaüstü uygulamaları](../windows/windows-desktop-applications-cpp.md)|Konsolun aksine Windows çalıştıran Masaüstü uygulamaları oluşturma|
|[(C++) DirectX kullanarak oyun oluşturmak için kaynaklar](../windows/resources-for-creating-a-game-using-directx.md)|C++ ile oyun oluşturmak için içerik bağlar.|
|[İzlenecek yol: Oluşturma ve statik bir kitaplık kullanılarak](../windows/walkthrough-creating-and-using-a-static-library-cpp.md)|Bir .lib ikili dosyasının nasıl oluşturulacağı.|
|[Nasıl yapılır: Windows 10 SDK’yı bir Windows Masaüstü Uygulamasında Kullanma](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows 10 SDK'sını kullanarak oluşturmak projenizi ayarlamak için adımları içerir.|

## <a name="related-articles"></a>İlgili Makaleler

|Başlık|Açıklama|
|-----------|-----------------|
|[Windows Geliştirme](http://go.microsoft.com/fwlink/p/?LinkId=262282)|Windows API'si ve COM hakkında bilgiler içerir (Bazı Windows API'leri ve üçüncü parti DLL'ler COM nesneleri olarak uygulanır.)|
|[Hilo: Windows 7 için C++ uygulamaları geliştirme](http://go.microsoft.com/fwlink/p/?LinkId=262284)|Atlıkarınca tarzı bir kullanıcı arabirimi oluşturmak için Windows animasyon ve Direct2D kullanan zengin istemci Windows Masaüstü uygulamasının nasıl oluşturulacağını açıklar.  Bu öğretici, Windows 7 beri güncelleştirilmemiş ancak yine de tam bir Win32 programlamaya giriş sağlar.|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual c++ in Visual Studio ve Visual C++ belgelerinin geri kalanı için bağlantıları anahtar özelliklerini açıklar.|

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++](../visual-cpp-in-visual-studio.md)