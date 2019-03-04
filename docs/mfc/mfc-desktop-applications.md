---
title: MFC Masaüstü Uygulamaları
ms.date: 11/04/2016
f1_keywords:
- MFC
- mfc
helpviewer_keywords:
- libraries, MFC
- class libraries, MFC
- MFC, about MFC
ms.assetid: 7101cb18-a681-495c-8f2b-069ad20c72f7
ms.openlocfilehash: 364f29406b2c00d26ecc4cc69060ed8ec21b743b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291292"
---
# <a name="mfc-desktop-applications"></a>MFC Masaüstü Uygulamaları

Microsoft Foundation Class (MFC) kitaplığı çoğunu Win32 ve COM API nesne yönelimli bir sarmalayıcı sağlar. Çok basit Masaüstü uygulamaları oluşturmak için kullanılabilir olsa da, birden çok denetimlerle daha karmaşık kullanıcı arabirimleri geliştirmek ihtiyacınız olduğunda en yararlı olur. MFC uygulamaları ile Office stili kullanıcı arabirimleri oluşturmak için kullanabilirsiniz.

MFC başvurusu, sınıflar, genel işlevleri, genel değişkenler ve Microsoft Foundation sınıf kitaplığını oluşturan makrolar kapsar.

Her sınıftaki ayrı hiyerarşi grafikleri taban sınıfların konumunu belirlemek için yararlıdır. MFC başvurusu genellikle devralınan üye işlevleri açıklamaz veya devralınan işleçleri. Bu işlevler hakkında daha fazla bilgi için hiyerarşi diyagramlarında düzenlenen temel sınıflara bakın.

Her sınıfın belgeleri sınıfa genel bakış, kategoriye ve üye işlevleri, aşırı yüklenmiş işleçler ve veri üyeleri konularına göre üye özeti içerir.

Genel ve korumalı sınıf üyeleri yalnızca normalde uygulama programlarında kullanıldıklarında belgelenir veya türetilmiş sınıflar. Sınıf üyelerinin tam listesi için sınıf üstbilgi dosyalarına bakın.

> [!IMPORTANT]
>  MFC sınıfları ve üyeleri, Windows çalışma zamanı ortamı içinde yürütülen uygulamalarda kullanılamaz.
>
>  Çok baytlı karakter kodlaması (MBCS) için MFC kitaplıkları (DLL'ler) artık Visual Studio'ya dahildir, ancak Visual Studio eklentisi olarak kullanılabilirler. Daha fazla bilgi için [MFC MBCS DLL eklentisi](mfc-mbcs-dll-add-on.md).

## <a name="in-this-section"></a>Bu Bölümde

[Kavramları](mfc-concepts.md)<br/>
MFC konularda kavramsal makaleler.

[Hiyerarşi Grafiği](hierarchy-chart.md)<br/>
Sınıf kitaplığındaki ilişkileri görsel olarak ayrıntıları.

[Sınıfına genel bakış](class-library-overview.md)<br/>
Sınıfları kategorilerine göre MFC Kitaplığı'ndaki listeler.

[İzlenecek Yollar](walkthroughs-mfc.md)<br/>
MFC kitaplık özellikleri ile ilgili çeşitli görevlerde size yol makaleler içerir.

[Teknik notlar](mfc-technical-notes.md)<br/>
Sınıf kitaplığı üzerinde MFC geliştirme takımı tarafından yazılan özel konulara bağlantılar sağlar.

[MFC için Özelleştirme](customization-for-mfc.md)<br/>
MFC uygulamanızı özelleştirmek için bazı ipuçları verilmektedir.

[Sınıflar](reference/mfc-classes.md)<br/>
Bağlantılar ve MFC sınıfları için üstbilgi dosyalarını sağlar.

[İç Sınıflar](reference/internal-classes.md)<br/>
MFC'de dahili olarak kullanılır. Bütünlük için bu bölümde söz konusu iç sınıfları açıklar ancak kodunuzda doğrudan kullanılması amaçlanmamıştır.

[Makroları ve genel öğeleri](reference/mfc-macros-and-globals.md)<br/>
Makrolar ve genel işlevler MFC Kitaplığı'ndaki bağlantılar sağlar.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](reference/structures-styles-callbacks-and-message-maps.md)<br/>
Yapılar, stiller, geri çağırmaları ve MFC Kitaplığı tarafından kullanılan ileti eşlemeleri bağlantılar sağlar.

[MFC Sihirbazları ve İletişim Kutuları](reference/mfc-wizards-and-dialog-boxes.md)<br/>
MFC uygulamaları oluşturmak için Visual Studio özellikleri için bir kılavuz.

[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>
Kullanıcı Arabirimi dizeleri ve iletişim kutusu düzeni gibi statik kullanıcı arabirimi verileri yönetmek için kaynak dosyalarını kullanma

## <a name="related-sections"></a>İlgili Bölümler

[Hiyerarşi Grafiği Kategorileri](hierarchy-chart-categories.md)<br/>
MFC hiyerarşi grafiğini kategoriye göre açıklar.

[ATL/MFC paylaşılan sınıfları](../atl-mfc-shared/atl-mfc-shared-classes.md)<br/>
MFC ve ATL arasında paylaşılan sınıfların bağlantılarını sağlar.

[MFC örnekleri](../visual-cpp-samples.md)<br/>
MFC'nin nasıl kullanılacağını gösteren örneklere bağlantılar sağlar.

[Visual C++ kitaplıkları başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
Visual C++ ile ATL, MFC, OLE DB Şablonları, C çalışma zamanı kitaplığı ve standart C++ Kitaplığı dahil olmak üzere sağlanan çeşitli kitaplıklara bağlantılar sağlar.

[Visual Studio’da hata ayıklama](/visualstudio/debugger/debugging-in-visual-studio.md)<br/>
Uygulamanızdaki veya saklı yordamları mantık hatalarını düzeltmek için Visual Studio hata ayıklayıcı kullanımına ilişkin bağlantılar sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ve ATL](mfc-and-atl.md)
