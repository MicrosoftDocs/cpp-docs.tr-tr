---
title: MFC'de Özel Durum İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- DAO [MFC], exceptions
- assertions [MFC], When to use exceptions
- exception handling [MFC], MFC
- resource allocation exception
- resources [MFC], allocating
- keywords [MFC], exception handling
- errors [MFC], detected by assertions
- ODBC exceptions [MFC]
- serialization [MFC], exceptions
- Automation [MFC], exceptions
- exception macros [MFC]
- predefined exceptions [MFC]
- C++ exception handling [MFC], enabling
- C++ exception handling [MFC], MFC applications
- requests for unsupported services [MFC]
- database exceptions [MFC]
- archive exceptions [MFC]
- MFC, exceptions
- C++ exception handling [MFC], types of
- macros [MFC], exception handling
- abnormal program execution [MFC]
- OLE exceptions [MFC], MFC exception handling
- error handling [MFC], exceptions and
- class libraries [MFC], exception support
- exceptions [MFC], MFC macros vs. C++ keywords
- memory [MFC], out-of-memory exceptions
- Windows [MFC], resource allocation exceptions
- macros [MFC], MFC exception macros
- function calls [MFC], results
- out-of-memory exceptions [MFC]
ms.assetid: 0926627d-2ba7-44a6-babe-d851a4a2517c
ms.openlocfilehash: e8c0f1feba566ef9b961edcfacb9124830f9851d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508617"
---
# <a name="exception-handling-in-mfc"></a>MFC'de Özel Durum İşleme

Bu makalede, MFC 'de kullanılabilen özel durum işleme mekanizmaları açıklanmaktadır. İki mekanizma vardır:

- C++özel durumlar, MFC sürüm 3,0 ve üzeri sürümlerde kullanılabilir

- MFC özel durum makroları, 1,0 ve üzeri MFC sürümlerinde kullanılabilir

MFC kullanarak yeni bir uygulama yazıyorsanız, C++ mekanizmasını kullanmanız gerekir. Mevcut uygulamanız zaten bu mekanizmayı yaygın olarak kullanıyorsa, makro tabanlı mekanizmayı kullanabilirsiniz.

Mevcut kodu MFC özel durum makroları yerine özel C++ durumlar kullanmak üzere kolayca dönüştürebilirsiniz. Kodunuzu ve yönergeleri dönüştürmenin avantajları, makalenin [özel durumları bölümünde açıklanmıştır: MFC özel durum makrolarından](../mfc/exceptions-converting-from-mfc-exception-macros.md)dönüştürme.

MFC özel durum makrolarını kullanarak zaten bir uygulama geliştirdiyseniz, yeni kodunuzda özel durumlar kullanırken C++ , mevcut kodunuzda bu makroları kullanmaya devam edebilirsiniz. Makale [özel durumları: Sürüm 3,0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md) ' deki özel durum makrolarında yapılan değişiklikler bunu yapmaya yönelik yönergeler sağlar.

> [!NOTE]
>  Kodunuzda özel C++ durum işlemeyi etkinleştirmek için, C++ projenin [Özellik sayfaları](../build/reference/property-pages-visual-cpp.md) Iletişim kutusunun C/C++ klasöründeki kod üretimi sayfasında özel durumları etkinleştir ' i seçin veya [/EHsc](../build/reference/eh-exception-handling-model.md) derleyici seçeneğini kullanın.

Bu makalede aşağıdaki konular ele alınmaktadır:

- [Özel durumlar ne zaman kullanılır?](#_core_when_to_use_exceptions)

- [MFC özel durum desteği](#_core_mfc_exception_support)

- [Özel durumlar hakkında daha fazla bilgi](#_core_further_reading_about_exceptions)

##  <a name="_core_when_to_use_exceptions"></a>Özel durumlar ne zaman kullanılır?

Program yürütme sırasında bir işlev çağrıldığında üç sonuç kategorisi oluşabilir: normal yürütme, hatalı yürütme veya olağan dışı yürütme. Her kategori aşağıda açıklanmıştır.

- Normal yürütme

   İşlev normal çalışabilir ve döndürebilir. Bazı işlevler, çağrı için işlevin sonucunu gösteren bir sonuç kodu döndürür. Olası sonuç kodları işlev için kesin olarak tanımlanmıştır ve işlevin olası sonuçlarının aralığını temsil eder. Sonuç kodu, başarılı veya başarısız olduğunu belirtebilir, hatta normal beklentiler aralığında olan belirli bir hata türünü gösterebilir. Örneğin, bir dosya durumu işlevi, dosyanın mevcut olmadığını belirten bir kod döndürebilir. Bir sonuç kodu beklenen birçok sonuçlardan birini temsil ettiğinden "hata kodu" teriminin kullanılmadığını unutmayın.

- Hatalı yürütme

   Çağıran, işleve bağımsız değişken geçirmeli veya işlevi uygunsuz bir bağlamda çağıran bir hata oluşturur. Bu durum bir hataya neden olur ve program geliştirme sırasında bir onaylama tarafından algılanmalıdır. (Onaylamalar hakkında daha fazla bilgi için bkz. [C/C++ ](/visualstudio/debugger/c-cpp-assertions)onaylar.)

- Olağan dışı yürütme

   Olağan dışı yürütme, programın denetimi dışındaki koşullarda (düşük bellek veya g/ç hataları gibi) işlevin sonucunu etkili bir şekilde etkileyen durumlar içerir. Olağan dışı durumlar, özel durumlar yakalanarak ve oluşturulurken işlenmelidir.

Özel durumların kullanılması özellikle olağan dışı yürütme için uygundur.

##  <a name="_core_mfc_exception_support"></a>MFC özel durum desteği

Özel durumları doğrudan kullanmanıza veya MFC özel durum makrolarını kullanmanıza bakılmaksızın, çerçeve veya uygulamanız tarafından oluşturulan [CException sınıfı](../mfc/reference/cexception-class.md) ya `CException`da türetilmiş nesneleri kullanırsınız. C++

Aşağıdaki tabloda, MFC tarafından sunulan önceden tanımlanmış özel durumlar gösterilmektedir.

|Özel durum sınıfı|Açıklama|
|---------------------|-------------|
|[CMemoryException Sınıfı](../mfc/reference/cmemoryexception-class.md)|Bellek yetersiz|
|[CFileException Sınıfı](../mfc/reference/cfileexception-class.md)|Dosya özel durumu|
|[CArchiveException Sınıfı](../mfc/reference/carchiveexception-class.md)|Arşiv/serileştirme özel durumu|
|[CNotSupportedException Sınıfı](../mfc/reference/cnotsupportedexception-class.md)|Desteklenmeyen hizmet isteğine yanıt|
|[CResourceException Sınıfı](../mfc/reference/cresourceexception-class.md)|Windows kaynak ayırma özel durumu|
|[CDaoException Sınıfı](../mfc/reference/cdaoexception-class.md)|Veritabanı özel durumları (DAO sınıfları)|
|[CDBException Sınıfı](../mfc/reference/cdbexception-class.md)|Veritabanı özel durumları (ODBC sınıfları)|
|[COleException Sınıfı](../mfc/reference/coleexception-class.md)|OLE özel durumları|
|[COleDispatchException Sınıfı](../mfc/reference/coledispatchexception-class.md)|Dağıtım (Otomasyon) özel durumları|
|[CUserException Sınıfı](../mfc/reference/cuserexception-class.md)|Kullanıcıyı bir ileti kutusuyla uyaran ve sonra genel bir [CException sınıfı](../mfc/reference/cexception-class.md) oluşturan özel durum|

> [!NOTE]
>  MFC hem özel C++ durumları hem de MFC özel durum makrolarını destekler. MFC, [yapılandırılmış özel durum işlemede](/windows/win32/debug/structured-exception-handling)anlatıldığı gıbı Windows NT yapılandırılmış özel durum IŞLEYICILERINI (SEH) doğrudan desteklemez.

##  <a name="_core_further_reading_about_exceptions"></a>Özel durumlar hakkında daha fazla bilgi

Aşağıdaki makalelerde özel durum teslim etmek için MFC kitaplığı kullanımı açıklanmaktadır:

- [Özel Durumlar: Özel Durumları Yakalama ve Silme](../mfc/exceptions-catching-and-deleting-exceptions.md)

- [Özel Durumlar: Özel Durum İçeriklerini İnceleme](../mfc/exceptions-examining-exception-contents.md)

- [Özel Durumlar: Özel Durumlardaki Nesneleri Boşaltma](../mfc/exceptions-freeing-objects-in-exceptions.md)

- [Özel Durumlar: Kendi İşlevlerinizden Özel Durumlar Oluşturma](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)

- [Özel Durumlar: Veritabanı Özel Durumları](../mfc/exceptions-database-exceptions.md)

- [Özel Durumlar: OLE Özel Durumları](../mfc/exceptions-ole-exceptions.md)

Aşağıdaki makalelerde, MFC özel durum makroları C++ özel durum anahtar sözcükleriyle karşılaştırılmaktadır ve kodunuzu nasıl uyarlayabileceğiniz açıklanmıştır:

- [Özel Durumlar: Sürüm 3.0'da Özel Durum Makrolarındaki Değişiklikler](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)

- [Özel Durumlar: MFC Özel Durum Makrolarından Dönüştürme](../mfc/exceptions-converting-from-mfc-exception-macros.md)

- [Özel Durumlar: MFC Makrolarını ve C++ Özel Durumlarını Kullanma](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ Özel Durum İşleme](../cpp/cpp-exception-handling.md)<br/>
[Nasıl yapılır: Kendi özel özel durum sınıflarımı oluştur](https://go.microsoft.com/fwlink/p/?linkid=128045)
