---
title: "Windows Forms MFC programlama farkları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], compared to MFC
ms.assetid: f3bfcf45-cfd4-45a4-8cde-5f4dbb18ee51
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 696e7684eb91abbf41e3f7a2e1df20b6fa7e5c17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="windows-formsmfc-programming-differences"></a>Windows Forms/MFC Programlama Farkları
Konular, [MFC içinde Windows formu kullanıcı denetimi kullanarak](../dotnet/using-a-windows-form-user-control-in-mfc.md) Windows Forms için MFC desteği açıklanmaktadır. .NET Framework veya programlama MFC bilmiyorsanız, bu konuda iki programlama farkları hakkında arka plan bilgileri sağlar.  
  
 Windows Forms, .NET Framework üzerinde Microsoft Windows uygulamaları oluşturmak üzere kullanılır. Bu çerçeve, zengin Windows tabanlı uygulamalar geliştirmenize olanak tanıyan sınıflar modern, nesne yönelimli, Genişletilebilir bir dizi sağlar. Windows Forms ile çok çeşitli veri kaynaklarına erişmek ve veri görüntüleme ve Windows Forms denetimlerini kullanarak veri düzenleme özellikleri sağlayan bir zengin istemci uygulaması oluşturabilir.  
  
 MFC'ye deneyimliyseniz, ancak, belirli türde bir Windows Forms henüz açıkça desteklenmeyen uygulamalar oluşturmak için kullanılabilir. Windows Forms uygulamaları MFC iletişim uygulamaları ile eşdeğerdir. Ancak, doğrudan tek belge arabirimi (SDI) birden çok belge arabirimi (MDI) OLE belge sunucu/kapsayıcı, ActiveX belgeleri, belge/görünüm desteği gibi diğer MFC uygulaması türlerini desteklemek için altyapı sağladıkları değil ve birden çok üst düzey arabirimi (MTI). Bu uygulamaları oluşturmak için kendi mantığınızı yazabilirsiniz.  
  
 Windows Forms uygulamaları hakkında daha fazla bilgi için bkz: [Windows Forms giriş](/dotnet/framework/winforms/windows-forms-overview).  
  
 MFC'de Windows Forms gösteren örnek bir uygulama için bkz: [MFC ve Windows Forms tümleştirme](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
 Aşağıdaki MFC görünümü veya belge ve komut yönlendirme özelliklerinin Windows Forms'ta eşdeğerleri yoktur:  
  
-   Tümleşik Kabuk  
  
     MFC Kabuk, bir belgeyi sağ tıklatın ve böyle fiiller açık olarak seçtiğinizde, düzenleme, veya yazdırma kullanan komut satırı bağımsız değişkenleri ve dinamik veri değişimi (DDE) komutları işler. Windows Forms Kabuk entegrasyonuna yok ve Kabuk fiillerini yanıtlamıyor.  
  
-   Belge şablonları  
  
     MFC'de belge şablonları bir çerçeve penceresinde (MDI, SDI veya MTI modu) içinde bulunan bir görünüm açtığınız belge ile ilişkilendirin. Windows Forms belge şablonları eşdeğeri vardır.  
  
-   Belgeler  
  
     MFC belge dosya türleri kaydettirir ve bir belgeyi Kabuğu'ndan açarken belge türü işler. Windows Forms hiçbir belge desteği yok.  
  
-   Belge durumları  
  
     MFC kirli durumları belge için korur. Uygulamayı kapatın, uygulamayı içeren son görünümü kapatın veya Windows'dan çıkın, bu nedenle, MFC belgeyi kaydetmek isteyip istemediğinizi sorar. Windows Forms hiçbir eşdeğer desteğe sahiptir.  
  
-   Komutlar  
  
     MFC komut kavramı vardır. Menü çubuğunda, araç ve bağlam menüsünden tüm aynı komutu, örneğin, kesme ve kopyalama çağırabilirsiniz. Windows Forms'ta (örneğin, bir menü öğesi); belirli bir kullanıcı Arabirimi öğesi sıkı bir şekilde ilişkili olayları komutlardır Bu nedenle, tüm komut olayları açıkça kanca gerekir. Windows Forms'ta tek bir işleyici ile birden çok olay de işleyebilir. Daha fazla bilgi için bkz: [Windows Forms'ta tek olay işleyicisine birden çok olay bağlanma](/dotnet/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms).  
  
-   Komut yönlendirme  
  
     MFC komut yönlendirme etkin görünüm veya belgeyi komutları işlemek üzere etkinleştirir. Aynı komutu genellikle farklı görünümleri için farklı anlamları olduğundan (örneğin, kopyalama farklı bir grafik düzenleyicisinde metin düzenleme görünümünde davranır), komutları etkin görünüm tarafından ele alınması gerekir. Windows Forms menüleri ve araç çubuklarını etkin görünümün yapısında hiçbir anlama sahip olduğundan, her bir görünüm türü için farklı bir işleyiciye sahip olamaz, **MenuItem.Click** ek iç kod yazma olmadan olaylar.  
  
-   Komut güncelleştirme mekanizması  
  
     MFC bir komut güncelleştirme mekanizmasına sahiptir. Bu nedenle, etkin görünüm veya belge (örneğin, etkinleştirme veya menü öğesi veya araç düğmesi devre dışı bırakma ve denetlendi) kullanıcı Arabirimi öğeleri durumunu sorumludur. Windows Forms hiçbir denk bir komut güncelleştirme mekanizması vardır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC içinde Windows formu kullanıcı denetimi kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Windows Forms izlenecek yollar](http://msdn.microsoft.com/en-us/fd44d13d-4733-416f-aefc-32592e59e5d9)