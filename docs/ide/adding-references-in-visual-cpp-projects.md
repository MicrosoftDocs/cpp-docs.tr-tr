---
title: "Visual C++ projelerine başvuru ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.References
dev_langs: C++
helpviewer_keywords:
- Add References Dialog Box (C++)
- .NET Framework (C++), Add References Dialog Box
ms.assetid: 12b8f571-0f21-40b3-9404-5318a57e9cb5
caps.latest.revision: "32"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7aacc70a74b7c7fccb66a0a8363a261f4a8f1ba3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="adding-references-in-visual-c-projects"></a>Visual C++ projelerine başvuru ekleme
Programların diğer ikili dosyaları, DLL'ler gibi içinde API'leri çağırmak yaygın Windows çalışma zamanı bileşenleri, uzantı SDK'ları, COM bileşenlerini ve .NET derlemelerini. Bu, diğer ikili dosyaları programınızın bulur biçimi hem de projenizi türünü ve ikili türüne bağlıdır.  
  
 Çözümünüzdeki, başka bir projeye göre oluşturulmuyor yerel bir DLL veya COM bileşeni kullanıyorsa yerel C++ projesinde LoadLibrary veya CoCreateInstance ikili dosya yolunu belirtin, aksi takdirde belirli Hoş Geldiniz bakarak bulun sistem izin kullandığınız l tanımlı konumları.  
  
 Projeleri UWP projeleri veya C + gibi diğer türlerinde +/ CLI projeleri veya ikili çözümünüzdeki başka bir projeye göre üretildiğinde eklediğiniz bir *başvuru* derleme, bileşen veya proje.   Bir başvuru temelde bulun ve ikili ile iletişim kurmak, program sağlayan veri kümesidir.       Visual Studio düşük düzey ayrıntılarını işler, bu, bir başvuru ekleyin. Başvurular bir C++ projesinde .NET Frameworkassemblies ayarlamak için (C + +/ CLI yalnızca), COM bileşenleri, çözüm dahil edilen diğer projelerin paylaşılan projeleri veya bağlı Hizmetleri, sağ tıklayın **başvuruları** düğümünde**Çözüm Gezgini** ortaya çıkarmak için **başvuru Yöneticisi**. Başvuru Yöneticisi'nde gördüğünüz proje türüne bağlı olarak farklılık gösterir.  
  
 Yerel C++ projesinde (ATL) kavram *başvuruları* yalnızca Çözümdeki tüm içinde gördüğünüz olacak şekilde paylaşılan projeleri de dahil olmak üzere diğer projeler için geçerlidir **başvuru Yöneticisi**:  
  
 ![Visual C# 43; &#43; Başvuru Yöneticisi &#40; ATL projeleri &#41; ] (../ide/media/visual-c---reference-manager--atl-projects-.png "Visual C++ başvuru Yöneticisi'ni (ATL projeleri)")  
  
 C + +/ CLI ya da evrensel Windows platformu proje başvuruları kavramı ikili dosyaları diğer projeleri yanı sıra daha fazla tür uygulandığı.  Bunlar tüm sunulan **başvuru Yöneticisi**.
  
## <a name="reference-properties"></a>Başvuru özellikleri  
 Her tür bir başvuru özelliklere sahiptir. Çözüm Gezgini'nde Başvurusu'ı seçip tuşuna basarak özelliklerini görüntüleyebilirsiniz **Alt + Enter**, veya başka sağ ve seçme **özellikleri**. Bazı özellikleri salt okunurdur ve bazı değiştirilebilir. Ancak, genellikle bu özellikleri el ile değiştirmeniz gerekmez.  
  
### <a name="activex-reference-properties"></a>ActiveX başvuru özellikleri  
 ActiveX başvuru özellikleri yalnızca COM bileşenlerini başvurular için kullanılabilir. Yalnızca bir COM bileşeni seçildiğinde bu özellikleri görüntülenir **başvuruları** bölmesi. Özellikleri değiştirilemez.  
  
 **Denetim tam yolu**  
 Başvurulan denetim dizin yolunu görüntüler.  
  
 **Denetim GUID**  
 ActiveX denetimi için GUID görüntülüyor.  
  
 **Sürüm denetimi**  
 Başvurulan ActiveX denetiminin sürümünü görüntüler.  
  
 **Tür kitaplığı adı**  
 Başvurulan tür kitaplığı adını görüntüler.  
  
 **Sarmalayıcı aracı**  
 Birlikte çalışma derlemesinden başvurulan COM kitaplığı veya ActiveX denetimi oluşturmak için kullanılan araç görüntüler.  
  
### <a name="assembly-reference-properties"></a>Derleme başvurusu özellikleri  
 Derleme başvurusu özellikler, yalnızca .NET Frameworkassemblies C + başvurular için kullanılabilir +/ CLI projeleri. Yalnızca .NET Frameworkassembly seçildiğinde bu özellikleri görüntülenir **başvuruları** bölmesi. Özellikleri değiştirilemez.  
  
 **Göreli yolu**  
 Proje dizininin başvurulan derleme göreli yolu görüntüler.  
  
### <a name="build-properties"></a>Özellikleri oluşturma  
 Aşağıdaki özellikler başvuruları çeşitli türlerde kullanılabilir. Bunlar, nasıl oluşturulacağını başvurularla belirtmenize olanak verir.  
  
 **Yerel kopyalama**  
 Otomatik olarak başvurulan bir derleme sırasında hedef konuma kopyalanıp kopyalanmayacağını belirtir.  
  
 **Yerel uydu derlemelerini kopyalayın**  
 Otomatik olarak başvurulan derlemeyi uydu derlemelerini derleme sırasında hedef konuma kopyalanıp kopyalanmayacağını belirtir. Yalnızca, kullanılan **kopya yerel** olan `true`.  
  
 **Başvuru derleme çıktı**  
 Bu derleme yapı işleminde kullanıldığını belirtir. Varsa `true`, derleme derleyici komut satırında derleme sırasında kullanılır.  
  
### <a name="project-to-project-reference-properties"></a>Proje Proje başvuru özellikleri  
 Aşağıdaki özellikleri tanımlama bir *proje proje başvurusu* seçildiyse projeden **başvuruları** aynı çözüm içinde başka bir projeye bölmesi. Daha fazla bilgi için bkz: [bir projedeki başvuruları yönetme](/visualstudio/ide/managing-references-in-a-project).  
  
 **Bağlantı kitaplık bağımlılıkları**  
 Bu özellik olduğunda **doğru**, proje sistemi bağımsız proje tarafından üretilen .lib dosyaları bağımlı projesine bağlar. Genellikle, belirteceksiniz **doğru**.  
  
 **Proje tanımlayıcısı**  
 Bağımsız proje benzersiz olarak tanımlar. Özellik, bir iç sistem değiştirilemez GUID değeridir.  
  
 **Kitaplık bağımlılık girişleri kullanın**  
 Bu özellik olduğunda **yanlış**, proje sistemi bağımlı projeye .obj dosyaları bağımsız proje tarafından üretilen kitaplığın bağlayacaksınız değil. Sonuç olarak, bu değer artımlı bağlantılandırma devre dışı bırakır. Genellikle, belirteceksiniz **False** için uygulama oluşturma çok sayıda bağımsız proje varsa uzun zaman alabilir.  
  
### <a name="reference-properties"></a>Başvuru özellikleri  
 Aşağıdaki özellikler COM ve .NET derleme başvurularını üzerinde bulunan ve değiştirilemez.  
  
 **Derleme adı**  
 Başvurulan derlemeyi derleme adını görüntüler.  
  
 **Kültür**  
 Seçili başvuruyu kültürünü görüntüler.  
  
 **Açıklama**  
 Seçili başvuruyu açıklamasını görüntüler.  
  
 **Tam yolu**  
 Başvurulan derlemeyi dizin yolunu görüntüler.  
  
 **Kimlik**  
 .NET Frameworkassemblies için tam yolunu görüntüler. COM bileşenleri için GUID görüntülüyor.  
  
 **Etiket**  
 Başvuru etiketini görüntüler.  
  
 **Ad**  
 Başvuru adını görüntüler.  
  
 **Ortak anahtar belirteci**  
 Başvurulan derlemeyi tanımlamak için kullanılan ortak anahtar belirteci görüntüler.  
  
 **Güçlü ad**  
 `true`Başvurulan derlemeyi tanımlayıcı ad varsa. Güçlü bir adlandırılmış derleme benzersiz olarak sürümlü ' dir.  
  
 **Sürüm**  
 Başvurulan derlemeyi sürümünü görüntüler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../ide/property-pages-visual-cpp.md)   
 [Proje özellikleriyle çalışma](../ide/working-with-project-properties.md)