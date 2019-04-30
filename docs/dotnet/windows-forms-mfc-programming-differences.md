---
title: Windows Forms / MFC programlama farkları
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], compared to MFC
ms.assetid: f3bfcf45-cfd4-45a4-8cde-5f4dbb18ee51
ms.openlocfilehash: 998485a3384512f57cf35fc264e2321fa0996728
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384458"
---
# <a name="windows-formsmfc-programming-differences"></a>Windows Forms/MFC Programlama Farkları

Konular, [MFC içinde Windows formu kullanıcı denetimi kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md) Windows Forms için MFC desteğini açıklar. Bu konu, .NET Framework veya MFC programlama ile ilgili bilgi sahibi değilseniz, iki programlama farkları hakkında arka plan bilgileri sağlar.

Windows Forms, .NET Framework üzerinde Microsoft Windows uygulamaları oluşturmak üzere kullanılır. Bu çerçeve, zengin Windows tabanlı uygulamalar geliştirmenize olanak tanır sınıfları modern, nesne yönelimli, Genişletilebilir sunmaktadır. Windows Forms ile çok çeşitli veri kaynaklarına erişebilir ve verileri görüntüleme ve Windows Forms denetimlerini kullanarak veri düzenleme özellikleri sağlayan bir zengin istemci uygulaması oluşturmak kullanabilirsiniz.

MFC için alışkın olduğunuz, ancak, belirli türdeki henüz Windows Forms'ta açıkça desteklenmeyen uygulamalar oluşturmak için kullanılabilir. Windows Forms uygulamaları MFC iletişim uygulamaları ile eşdeğerdir. Ancak, bunlar doğrudan tek belgeli arabirimi (SDI), Çok Belgeli Arabirim (MDI), sunucu/kapsayıcı OLE belge, ActiveX belgeleri ve belge/görünüm destek gibi diğer MFC Uygulama türlerini desteklemek için olan altyapının sağlanması değil ve birden çok en üst düzey arabirimi (MTI). Bu uygulamaları oluşturmak için kendi mantığını yazabilirsiniz.

Windows Forms uygulamaları hakkında daha fazla bilgi için bkz: [Windows Forms giriş](/dotnet/framework/winforms/windows-forms-overview).

MFC'de Windows formlarını gösteren örnek bir uygulama için bkz. [MFC ve Windows Forms tümleştirme](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).

Aşağıdaki MFC görünümü veya belge ve yönlendirme özelliklerinin komutu eşdeğerleri Windows Forms'ta yoktur:

- Shell tümleştirmesi

   MFC Kabuk belgeye sağ tıklayın ve gibi eylemler açık olarak seçin, düzenlemek veya yazdırma kullanan komut satırı bağımsız değişkenleri ve dinamik veri değişimi (DDE) komutları işler. Windows Forms Kabuk entegrasyonuna ve Kabuk fiillerini yanıt vermiyor.

- Belge şablonları

   MFC içinde belge şablonları bir çerçeve penceresinde (modunda MDI, SDI veya MTI) bulunan bir görünüm açtığınız belge ile ilişkilendirin. Windows Forms eşdeğeri belge şablonları için vardır.

- Belgeler

   MFC belge dosya türleri kaydettirir ve bir belge türü Kabuğu'ndan bir belge açılırken işler. Windows Forms hiçbir belge desteği yok.

- Belge durumları

   MFC belge için olumsuz durumlar tutar. Bu nedenle, uygulamayı kapatın, uygulamayı içeren son görünümü kapatın veya Windows ' çıkmak MFC belge kaydetmenizi ister. Windows Forms eşdeğer desteği vardır.

- Komutlar

   MFC komutlarını kavramı vardır. Menü çubuğu, araç ve bağlam menüsünden Tüm kesme ve kopyalama aynı komutu çalıştırabilirsiniz. Windows Forms'ta sıkı şekilde bağlı (örneğin, bir menü öğesi); belirli bir kullanıcı Arabirimi öğesi olaylardan komutlardır Bu nedenle, tüm komut olayları açıkça kanca gerekir. Windows Forms'ta tek bir işleyici ile birden çok olayı de işleyebilirsiniz. Daha fazla bilgi için [Windows Forms'ta tek bir olay işleyicisine birden çok olayı bağlanma](/dotnet/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms).

- Komut yönlendirme

   MFC komut yönlendirme etkin görünüm veya belge komutları işlemek üzere etkinleştirir. Aynı komutu genellikle farklı görünümleri için farklı anlamlara sahip olduğundan (örneğin, kopyalama farklı metin düzenleme görünümünde bir grafik düzenleyicisinde davranır), komutları etkin görünüm tarafından ele alınması gerekir. Windows Forms menüleri ve araç çubuklarını etkin görünüm devralınan hiçbir bilgiye sahip olduğundan, her bir görünüm türü için farklı bir işleyici olamaz, **MenuItem.Click** iç ek bir kod yazmadan olayları.

- Komut güncelleştirme mekanizması

   MFC, bir komut güncelleştirme mekanizması vardır. Bu nedenle, etkin görünüm veya belge (örneğin, etkinleştirme veya bir menü öğesi veya araç düğmesi devre dışı bırakma ve denetlendi) Arabirim öğelerinin durumu sorumludur. Windows Forms hiçbir denk bir komut güncelleştirme mekanizması vardır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC içinde Windows Formu Kullanıcı Denetimi Kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md)
