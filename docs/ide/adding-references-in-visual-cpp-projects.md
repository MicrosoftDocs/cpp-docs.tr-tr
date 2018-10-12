---
title: Visual C++ projelerine başvuru ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.References
dev_langs:
- C++
helpviewer_keywords:
- Add References Dialog Box (C++)
- .NET Framework (C++), Add References Dialog Box
ms.assetid: 12b8f571-0f21-40b3-9404-5318a57e9cb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b372959105407074cd2a7295837e2c47ef629da7
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162171"
---
# <a name="adding-references-in-visual-c-projects"></a>Visual C++ projelerine başvuru ekleme

DLL dosyaları gibi diğer ikili API'lere çağrılacak programları için yaygın olarak görülür Windows çalışma zamanı bileşenleri, uzantı SDK'ları, COM bileşenleri ve .NET derlemeleri. Bu, diğer ikili dosyaları programınızın bulur bir şekilde hem proje türü ve ikili türü bağlıdır.

Çözümünüzdeki başka bir proje tarafından üretilmekte olan olmayan yerel bir DLL veya COM bileşeni kullanıyorsa yerel bir C++ projesinde LoadLibrary veya CoCreateInstance ikili dosya yolunu belirtin, aksi takdirde belirli Hoş Geldiniz bakarak bulun sistem ayarlasın kullandığınız m tanımlı konumları.

Diğer türden projeleri gibi UWP projeleri veya C + +/ CLI projeleri veya çözümünüzdeki başka bir proje tarafından üretilen ikili, eklediğiniz bir *başvuru* derleme, bileşen veya proje.   Aslında, bulun ve ikili ile iletişim kurmak için programınızı sağlayan veri kümesi bir başvurudur.       Bir başvuru eklediğinizde, Visual Studio düşük düzey ayrıntıları işler. Bir C++ projesi başvuruları .NET Frameworkassemblies için ayarlanacak (C + +/ CLI yalnızca), COM bileşenlerini, diğer projeleri çözüm gibi proje paylaşılan ya da bağlı hizmetler, sağ **başvuruları** düğümünde**Çözüm Gezgini** ortaya çıkarmak için **başvuru Yöneticisi**. Başvuru Yöneticisi'nde gördüklerinizi, proje türüne bağlı olarak farklılık gösterir.

Yerel C++ projesinde (ATL) kavramı *başvuruları* yalnızca tüm içinde gördüğünüz şekilde paylaşılan projeler dahil olmak üzere, çözümdeki diğer projelere uygulanır **başvuru Yöneticisi**:

![Visual C&#43; &#43; başvuru Yöneticisi &#40;ATL projeleri&#41;](../ide/media/visual-c---reference-manager--atl-projects-.png "Visual C++ başvuru Yöneticisi (ATL projeleri)")

C + +/ CLI veya evrensel Windows platformu projesi başvuruları kavramını ikili dosyalarının çözümdeki diğer projelerin yanı sıra daha fazla tür uygulandığı.  Bu tüm sunulan **başvuru Yöneticisi**.

## <a name="reference-properties"></a>Başvuru özellikleri

Her tür başvurusu özellikleri vardır. Çözüm Gezgini'nde reference'ı seçip tuşuna basarak özelliklerini görüntüleyebilirsiniz **Alt + Enter**, veya başka sağ ve seçme **özellikleri**. Bazı özellikler salt okunurdur ve bazı değiştirilebilir. Ancak, genellikle bu özellikleri el ile değiştirmeniz gerekmez.

### <a name="activex-reference-properties"></a>ActiveX başvuru özellikleri

ActiveX başvurusu özellikleri yalnızca COM bileşenleri başvurular için kullanılabilir. Bu özellikler yalnızca bir COM bileşeni seçildiğinde görüntülenen **başvuruları** bölmesi. Özellikleri değiştirilemez.

- **Denetim tam yolu**

   Başvurulan denetimin dizin yolunu görüntüler.

- **Denetim GUID'i**

   ActiveX denetimi için GUID görüntüler.

- **Denetim sürümü**

   Başvurulan ActiveX denetiminin sürümünü görüntüler.

- **Tür kitaplığı adı**

   Başvurulan tür kitaplığının adı görüntüler.

- **Sarmalayıcı aracı**

   Başvurulan COM kitaplığından ya da ActiveX denetiminden birlikte çalışma derlemesi oluşturmak için kullanılan araç görüntüler.

### <a name="assembly-reference-properties"></a>Bütünleştirilmiş kod başvuru özellikleri

Derleme başvurusu özellikleri yüklenebilir yalnızca başvurular .NET Frameworkassemblies C + +/ CLI projeleri. Bu özellikler yalnızca .NET Frameworkassembly seçildiğinde görüntülenen **başvuruları** bölmesi. Özellikleri değiştirilemez.

- **Göreli yolu**

   Proje dizininden başvurulan derlemeye göreli yolunu görüntüler.

### <a name="build-properties"></a>Derleme özellikleri

Aşağıdaki özellikler, çeşitli türlerdeki başvurular üzerinde kullanılabilir. Derleme başvuruları ile nasıl belirtmenize olanak tanırlar.

- **Yerele Kopyala**

   Başvurulan derlemenin bilgisayarın bir yapı sırasında hedef konuma otomatik olarak kopyalanıp kopyalanmayacağını belirtir.

- **Yerel uydu derlemelerini Kopyala**

   Başvurulan derlemenin uydu derlemelerinin bilgisayarın bir yapı sırasında hedef konuma otomatik olarak kopyalanıp kopyalanmayacağını belirtir. Yalnızca **Yereli Kopyala** olduğu **true**.

- **Başvuru bütünleştirilmiş kodu çıkışı**

   Bu derlemenin yapı işleminde kullanıldığını belirtir. Varsa **true**, derleme yapı sırasında derleyici komut satırında kullanılır.

### <a name="project-to-project-reference-properties"></a>Projeden projeye başvuru özellikleri

Aşağıdaki özellikleri tanımlayan bir *projeden projeye başvuru* seçili projeden **başvuruları** aynı çözümdeki başka bir projeye bölmesi. Daha fazla bilgi için [bir projedeki başvuruları yönetme](/visualstudio/ide/managing-references-in-a-project).

- **Bağlantı kitaplığı bağımlılıkları**

   Bu özellik olduğunda **True**, proje sistemi bağımsız proje tarafından üretilen .lib dosyaları bağımlı projesine bağlar. Genellikle, belirteceği **True**.

- **Proje tanımlayıcısı**

   Bağımsız projenin benzersiz olarak tanımlar. Özelliği bir iç sistem değiştirilemez GUID değeridir.

- **Kitaplık bağımlılığı girişlerini kullan**

   Bu özellik olduğunda **False**, proje sistemi bağımlı projeye bağımsız proje tarafından üretilen kitaplığı .obj dosyaları bağlayacaksınız değil. Sonuç olarak, bu değer artımlı bağlamayı devre dışı bırakır. Genellikle, belirteceği **False** çünkü uygulama oluşturma çok sayıda bağımsız proje ise bir uzun zaman alabilir.

### <a name="reference-properties"></a>Başvuru özellikleri

Aşağıdaki özellikleri, COM ve .NET derleme başvurularını bulunur ve değiştirilemez.

- **Derleme adı**

   Başvurulan derlemenin derleme adını görüntüler.

- **Kültür**

   Seçilen başvurunun kültürü görüntüler.

- **Açıklama**

   Seçilen başvurunun açıklaması görüntüler.

- **Tam yolu**

   Başvurulan derlemenin dizin yolunu görüntüler.

- **Kimlik**

   .NET Frameworkassemblies için tam yolunu görüntüler. COM bileşenleri için GUID görüntüler.

- **Etiket**

   Başvurunun etiketi görüntüler.

- **Ad**

   Başvuru adını görüntüler.

- **Ortak anahtar belirteci**

   Başvurulan derlemeyi tanımlamak için kullanılan ortak anahtar belirtecini görüntüler.

- **Tanımlayıcı ad**

   `true` başvurulan derlemenin tanımlayıcı ad varsa. Bir tanımlayıcı adlı derleme sürümlüdür.

- **Sürüm**

   Başvurulan derlemenin sürümünü gösterir.

## <a name="see-also"></a>Ayrıca Bkz.

[Özellik Sayfaları](../ide/property-pages-visual-cpp.md)<br>
[Proje Özellikleriyle Çalışma](../ide/working-with-project-properties.md)