---
title: MFC Masaüstü Uygulamaları
ms.date: 07/28/2019
f1_keywords:
- MFC
helpviewer_keywords:
- libraries, MFC
- class libraries, MFC
- MFC, about MFC
ms.assetid: 7101cb18-a681-495c-8f2b-069ad20c72f7
ms.openlocfilehash: 3811fdcf278129ee72872ea489b42f8389957761
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359350"
---
# <a name="mfc-desktop-applications"></a>MFC Masaüstü Uygulamaları

Microsoft Hazırlık Sınıfı (MFC) Kitaplığı, Win32 ve COM API'lerinin çoğunda nesne yönelimli bir sarıcı sağlar. Çok basit masaüstü uygulamaları oluşturmak için kullanılabilir olsa da, birden çok denetimile daha karmaşık kullanıcı arabirimleri geliştirmeniz gerektiğinde en kullanışlıdır. Office tarzı kullanıcı arabirimleriyle uygulamalar oluşturmak için MFC'yi kullanabilirsiniz. Windows platformunun kendisiyle ilgili belgeler için [Windows belgelerine](/windows/index)bakın. MFC olmadan C++'da Windows uygulamaları oluşturma hakkında daha fazla bilgi için [Win32 API'sini kullanarak masaüstü Windows uygulamaları oluşturun'e](/windows/win32/index)bakın.

MFC Başvurusu, Microsoft Hazırlık Sınıfı Kitaplığını oluşturan sınıfları, genel işlevleri, genel değişkenleri ve makroları kapsar.

Her sınıfla birlikte verilen tek tek hiyerarşi grafikleri temel sınıfları bulmak için yararlıdır. MFC Başvurusu genellikle devralınan üye işlevleri veya devralınan işleçleri tanımlamaz. Bu işlevler hakkında bilgi için, hiyerarşi diyagramlarında gösterilen temel sınıflara bakın.

Her sınıf için belgeler bir sınıf genel bakışı, kategoriye göre bir üye özeti ve üye işlevler, aşırı yüklenen işleçler ve veri üyeleri için konular içerir.

Ortak ve korumalı sınıf üyeleri yalnızca normalde uygulama programlarında veya türemiş sınıflarda kullanıldıklarında belgelenir. Sınıf üyelerinin tam listesi için sınıf üstbilgi dosyalarına bakın.

> [!IMPORTANT]
> MFC sınıfları ve üyeleri, Windows Runtime ortamında çalışan uygulamalarda kullanılamaz.
>
> Çok bayt karakter kodlaması (MBCS) için MFC kitaplıkları (DLs) artık Visual Studio'ya dahil değildir, ancak Visual Studio eklentisi olarak kullanılabilir. Daha fazla bilgi için [MFC MBCS DLL Eklentisi'ne](mfc-mbcs-dll-add-on.md)bakın.

## <a name="in-this-section"></a>Bu Bölümde

[Kavramlar](mfc-concepts.md)<br/>
MFC konuları yla ilgili kavramsal makaleler.

[Hiyerarşi Grafiği](hierarchy-chart.md)<br/>
Sınıf kitaplığındaki sınıf ilişkilerini görsel olarak ayrıntılarıyla anlatır.

[Sınıfa Genel Bakış](class-library-overview.md)<br/>
MFC Kitaplığı'ndaki sınıfları kategoriye göre listeler.

[İzlenecek Yollar](walkthroughs-mfc.md)<br/>
MFC kitaplık özellikleriyle ilişkili çeşitli görevlerde size yol gösteren makaleler içerir.

[Teknik Notlar](mfc-technical-notes.md)<br/>
Sınıf kitaplığında MFC geliştirme ekibi tarafından yazılan özel konulara bağlantılar sağlar.

[MFC için Özelleştirme](customization-for-mfc.md)<br/>
MFC uygulamanızı özelleştirmek için bazı ipuçları sağlar.

[Sınıflar](reference/mfc-classes.md)<br/>
MFC sınıfları için bağlantı ve üstbilgi dosya bilgileri sağlar.

[İç Sınıflar](reference/internal-classes.md)<br/>
MFC'de dahili olarak kullanılır. Tamolmak için, bu bölümde bu iç sınıflar açıklanır, ancak bunlar doğrudan kodunuzda kullanılmak üzere tasarlanmamıştır.

[Makrolar ve Küreseller](reference/mfc-macros-and-globals.md)<br/>
MFC Kitaplığı'ndaki makrolara ve genel işlevlere bağlantılar sağlar.

[Yapılar, Stiller, Geri Aramalar ve İleti Haritaları](reference/structures-styles-callbacks-and-message-maps.md)<br/>
MFC Kitaplığı tarafından kullanılan yapılara, stillere, geri aramalara ve ileti haritalarına bağlantılar sağlar.

[MFC Sihirbazları ve İletişim Kutuları](reference/mfc-wizards-and-dialog-boxes.md)<br/>
MFC uygulamaları oluşturmak için Visual Studio özellikleri için bir rehber.

[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>
Kullanıcı arabirimleri dizeleri ve iletişim kutusu düzeni gibi statik kullanıcı arabirimi verilerini yönetmek için kaynak dosyaları nasıl kullanılır.

## <a name="related-sections"></a>İlgili Bölümler

[Hiyerarşi Grafik Kategorileri](hierarchy-chart-categories.md)<br/>
MFC hiyerarşi grafiğini kategoriye göre açıklar.

[ATL/MFC Paylaşılan Sınıfları](../atl-mfc-shared/atl-mfc-shared-classes.md)<br/>
MFC ve ATL arasında paylaşılan sınıflara bağlantılar sağlar.

[MFC Örnekleri](../overview/visual-cpp-samples.md#mfc-samples)<br/>
MFC'nin nasıl kullanılacağını gösteren örneklere bağlantılar sağlar.

[Visual C++ Kütüphaneler Referans](../standard-library/cpp-standard-library-reference.md)<br/>
ATL, MFC, OLE DB Şablonları, C çalışma zamanı kitaplığı ve C++ Standart Kitaplığı gibi Visual C++ile sağlanan çeşitli kitaplıklara bağlantılar sağlar.

[Visual Studio’da hata ayıklama](/visualstudio/debugger/debugging-in-visual-studio)<br/>
Uygulamanızdaki veya depolanan yordamları düzeltmek için Visual Studio hata ayıklayıcısını kullanmaya bağlantılar sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ve ATL](mfc-and-atl.md)
