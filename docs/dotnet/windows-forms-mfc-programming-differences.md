---
title: Windows Forms-MFC programlama farkları
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], compared to MFC
ms.assetid: f3bfcf45-cfd4-45a4-8cde-5f4dbb18ee51
ms.openlocfilehash: 52de36217a5ab47eddcbe1abd6617860dcb910b8
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/06/2019
ms.locfileid: "73704184"
---
# <a name="windows-formsmfc-programming-differences"></a>Windows Forms/MFC Programlama Farkları

[MFC 'de Windows form kullanıcı denetimi kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md) konuları, WINDOWS Forms için MFC desteğini anlatmaktadır. .NET Framework veya MFC programlamasına alışkın değilseniz, bu konu iki arasındaki programlama farkları hakkında arka plan bilgileri sağlar.

Windows Forms, .NET Framework Microsoft Windows uygulamaları oluşturmak içindir. Bu çerçeve, zengin Windows tabanlı uygulamalar geliştirmenize olanak sağlayan modern, nesne odaklı, genişletilebilir bir sınıf kümesi sağlar. Windows Forms sayesinde, çok çeşitli veri kaynaklarına erişebilen ve Windows Forms denetimleri kullanarak veri görüntüleme ve veri düzenleme olanakları sağlayan zengin bir istemci uygulaması oluşturabilirsiniz.

Ancak, MFC 'yi alışkın değilseniz, Windows Forms henüz açıkça desteklenmeyen belirli türde uygulamalar oluşturmak için kullanılabilir. Windows Forms uygulamalar MFC iletişim uygulamalarına eşdeğerdir. Ancak, OLE belge sunucusu/kapsayıcısı, ActiveX belgeleri, tek belge arabirimi (SDI), birden çok belge arabirimi (MDI) için belge/görünüm desteği ve birden çok üst düzey arabirim (MTı). Bu uygulamaları oluşturmak için kendi mantığınızı yazabilirsiniz.

Windows Forms uygulamalar hakkında daha fazla bilgi için bkz. [Windows Forms giriş](/dotnet/framework/winforms/windows-forms-overview).

MFC ile kullanılan Windows Forms gösteren örnek bir uygulama için bkz. [MFC ve Windows Forms tümleştirmesi](https://www.microsoft.com/en-us/download/details.aspx?id=2113).

Aşağıdaki MFC görünümü veya belge ve komut yönlendirme özelliklerinin Windows Forms eşdeğerleri yoktur:

- Kabuk tümleştirmesi

   MFC, bir belgeye sağ tıklayıp açık, düzenleme veya yazdırma gibi fiilleri seçtiğinizde, kabuğun kullandığı dinamik veri değişimi (DDE) komutlarını ve komut satırı bağımsız değişkenlerini işler. Windows Forms kabuk tümleştirmesi yoktur ve kabuk fiillerine yanıt vermez.

- Belge şablonları

   MFC 'de belge şablonları, açtığınız belgeyle birlikte çerçeve penceresinde bulunan bir görünümü (MDI, SDI veya MTı modunda) ilişkilendirir. Windows Forms belge şablonlarına denk değildir.

- Belgeler

   MFC, belge dosya türlerini kaydeder ve kabuktan bir belge açarken belge türünü işler. Windows Forms belge desteği yok.

- Belge durumları

   MFC, belge için kirli durumları korur. Bu nedenle, uygulamayı kapattığınızda, uygulamayı içeren son görünümü kapatın veya Windows 'tan çıktığınızda, MFC belgeyi kaydetmenizi ister. Windows Forms eşdeğer bir desteği yoktur.

- Komutlar

   MFC 'nin komut kavramı vardır. Menü çubuğu, araç çubuğu ve bağlam menüsü, hepsi de aynı komutu çağırabilir, örneğin kes ve Kopyala. Windows Forms, komutlar belirli bir kullanıcı arabirimi öğesinden (bir menü öğesi gibi) sıkı bir şekilde bağlantılı olaylardır; Bu nedenle, tüm komut olaylarını açıkça yedeklemeniz gerekir. Ayrıca, Windows Forms içinde tek bir işleyiciyle birden çok olayı işleyebilirsiniz. Daha fazla bilgi için bkz. [Windows Forms birden çok olayı tek bir olay Işleyicisine bağlama](/dotnet/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms).

- Komut yönlendirme

   MFC komut yönlendirmesi, etkin görünüm veya belgenin komut işlemesini sağlar. Aynı komutun farklı görünümler için genellikle farklı anlamları olduğundan (örneğin, kopyalama metin düzenleme görünümünde grafik düzenleyicisinden farklı şekilde davrandığı için), komutların etkin görünüm tarafından işlenmesi gerekir. Windows Forms menülerde ve araç çubuklarında etkin görünüm hakkında hiç anlaşılmadığından, MenuItem 'ınız için her bir görünüm türü için farklı bir işleyiciniz olamaz **.** ek iç kod yazmadan olaylar ' a tıklayın.

- Komut güncelleştirme mekanizması

   MFC 'nin bir komut güncelleştirme mekanizması vardır. Bu nedenle, etkin görünüm veya belge, Kullanıcı arabirimi öğelerinin durumundan sorumludur (örneğin, bir menü öğesini veya araç düğmesini etkinleştirme veya devre dışı bırakma ve denetlenen durumlar). Windows Forms bir komut güncelleştirme mekanizmasına denk değildir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC içinde Windows Formu Kullanıcı Denetimi Kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md)
