---
title: MFC Masaüstü Uygulamaları
ms.date: 07/28/2019
f1_keywords:
- MFC
- mfc
helpviewer_keywords:
- libraries, MFC
- class libraries, MFC
- MFC, about MFC
ms.assetid: 7101cb18-a681-495c-8f2b-069ad20c72f7
ms.openlocfilehash: f23a41a0dbaedb7063617accee3afe4ba833d59c
ms.sourcegitcommit: 720b74dddb1cdf4e570d55103158304ee1df81f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/29/2019
ms.locfileid: "68607528"
---
# <a name="mfc-desktop-applications"></a>MFC Masaüstü Uygulamaları

Microsoft Foundation Class (MFC) kitaplığı, Win32 ve COM API 'Lerinin büyük bir bölümü için nesne odaklı bir sarmalayıcı sağlar. Çok basit masaüstü uygulamaları oluşturmak için kullanılabilir olsa da, çok sayıda denetim ile daha karmaşık kullanıcı arabirimleri geliştirmeniz gerektiğinde bu en yararlı seçenektir. MFC 'yi, Office stilinde Kullanıcı arabirimleriyle uygulamalar oluşturmak için kullanabilirsiniz. Windows platformunun belgeleri için, bkz. [Windows belgeleri](/windows/index). MFC olmadan uygulamasında C++ Windows uygulamaları oluşturma hakkında bilgi için, bkz. [Win32 API kullanarak masaüstü Windows uygulamaları oluşturma](/windows/win32/index).

MFC başvurusu, Microsoft Foundation Class Kitaplığı oluşturan sınıfları, küresel işlevleri, genel değişkenleri ve makroları içerir.

Her sınıfa dahil edilen tek tek hiyerarşi grafikleri, temel sınıfların bulunması için faydalıdır. MFC başvurusu genellikle devralınan üye işlevleri veya devralınan işleçleri tanımlamaz. Bu işlevler hakkında daha fazla bilgi için, hiyerarşi diyagramlarında gösterilen temel sınıflara bakın.

Her sınıfın belgeleri, bir sınıfa genel bakış, kategoriye göre üye Özeti ve üye işlevleri, aşırı yüklenmiş işleçler ve veri üyeleri için konular içerir.

Ortak ve korunan sınıf üyeleri yalnızca uygulama programlarında veya türetilmiş sınıflarda normalde kullanıldıkları zaman belgelenmiştir. Sınıf üyelerinin tamamı listesi için sınıf üst bilgisi dosyalarına bakın.

> [!IMPORTANT]
>  MFC sınıfları ve üyeleri Windows Çalışma Zamanı ortamda yürütülen uygulamalarda kullanılamaz.
>
>  Çok baytlı karakter kodlaması (MBCS) için MFC kitaplıkları (dll) artık Visual Studio 'ya dahil değildir ancak Visual Studio eklentisi olarak kullanılabilir. Daha fazla bilgi için bkz. [MFC MBCS dll eklentisi](mfc-mbcs-dll-add-on.md).

## <a name="in-this-section"></a>Bu Bölümde

[Tiren](mfc-concepts.md)<br/>
MFC konularındaki kavramsal makaleler.

[Hiyerarşi Grafiği](hierarchy-chart.md)<br/>
Sınıf kitaplığındaki sınıf ilişkilerinin görsel olarak ayrıntılarına bakın.

[Sınıfa genel bakış](class-library-overview.md)<br/>
MFC kitaplığındaki sınıfları kategoriye göre listeler.

[İzlenecek Yollar](walkthroughs-mfc.md)<br/>
MFC Kitaplığı özellikleriyle ilişkili çeşitli görevlerde size kılavuzluk eden makaleler içerir.

[Teknik notlar](mfc-technical-notes.md)<br/>
Sınıf kitaplığındaki MFC geliştirme ekibi tarafından yazılan özelleştirilmiş konuların bağlantılarını sağlar.

[MFC için Özelleştirme](customization-for-mfc.md)<br/>
MFC uygulamanızı özelleştirmek için bazı ipuçları sağlar.

[Sınıflar](reference/mfc-classes.md)<br/>
MFC sınıfları için bağlantılar ve üstbilgi dosyası bilgilerini sağlar.

[İç Sınıflar](reference/internal-classes.md)<br/>
MFC 'de dahili olarak kullanılır. Bu bölümde, bu bölüm bu iç sınıfları açıklar ancak doğrudan kodunuzda kullanılmaya yönelik değildir.

[Makrolar ve genel öğeler](reference/mfc-macros-and-globals.md)<br/>
MFC kitaplığındaki makrolar ve genel işlevlere bağlantılar sağlar.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](reference/structures-styles-callbacks-and-message-maps.md)<br/>
MFC kitaplığı tarafından kullanılan yapılar, stiller, geri çağrılar ve ileti eşlemelerine bağlantılar sağlar.

[MFC Sihirbazları ve İletişim Kutuları](reference/mfc-wizards-and-dialog-boxes.md)<br/>
MFC uygulamaları oluşturmak için Visual Studio özelliklerine yönelik bir kılavuz.

[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>
UI dizeleri ve iletişim kutusu düzeni gibi statik kullanıcı arabirimi verilerini yönetmek için kaynak dosyalarını kullanma.

## <a name="related-sections"></a>İlgili Bölümler

[Hiyerarşi Grafiği Kategorileri](hierarchy-chart-categories.md)<br/>
Kategoriye göre MFC hiyerarşi grafiğini açıklar.

[ATL/MFC paylaşılan sınıfları](../atl-mfc-shared/atl-mfc-shared-classes.md)<br/>
MFC ve ATL arasında paylaşılan sınıflara bağlantılar sağlar.

[MFC örnekleri](../overview/visual-cpp-samples.md)<br/>
MFC 'nin nasıl kullanılacağını gösteren örneklere bağlantılar sağlar.

[Visual C++ kitaplıkları başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
ATL, MFC, OLE DB şablonları, C çalışma C++zamanı kitaplığı ve C++ standart kitaplık dahil olmak üzere görsele sağlanan çeşitli kitaplıkların bağlantılarını sağlar.

[Visual Studio’da hata ayıklama](/visualstudio/debugger/debugging-in-visual-studio)<br/>
Uygulamanızdaki veya saklı yordamlardaki mantık hatalarını düzeltmek için Visual Studio hata ayıklayıcısını kullanma bağlantıları sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ve ATL](mfc-and-atl.md)
