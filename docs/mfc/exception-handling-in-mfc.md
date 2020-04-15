---
title: MFC'de Özel Durum İşleme
ms.date: 11/19/2019
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
ms.openlocfilehash: d339ec98dabc6cb24fc7106c4c7238cd6a14a71b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365528"
---
# <a name="exception-handling-in-mfc"></a>MFC'de Özel Durum İşleme

Bu makalede, MFC'de bulunan özel durum işleme mekanizmaları açıklanmaktadır. İki mekanizma mevcuttur:

- C++ özel durumları, MFC sürüm 3.0 ve sonraki sürümlerde mevcuttur

- MFC özel durum makroları, MFC sürümleri 1.0 ve daha sonra mevcuttur

MFC kullanarak yeni bir uygulama yazıyorsanız, C++ mekanizmasını kullanmanız gerekir. Varolan uygulamanız zaten bu mekanizmayı kapsamlı olarak kullanıyorsa makro tabanlı mekanizmayı kullanabilirsiniz.

Varolan kodu MFC özel durum makroları yerine C++ özel durumlarını kullanmak üzere kolayca dönüştürebilirsiniz. Kodunuzu ve bunu yapmak için yönergeleridönüştürmenin avantajları özel durumlar makalesinde [açıklanmıştır: MFC Özel Durum Makrolarından dönüştürme.](../mfc/exceptions-converting-from-mfc-exception-macros.md)

MFC özel durum makrolarını kullanarak zaten bir uygulama geliştirdiyseniz, yeni kodunuzda C++ özel durumları kullanırken bu makroları varolan kodunuzda kullanmaya devam edebilirsiniz. Özel [Durumlar: Sürüm 3.0'daki Özel Durum Makrolarında yapılan değişiklikler,](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md) bunu yapmak için yönergeler verir.

> [!NOTE]
> Kodunuzda C++ özel durum işlemeyi etkinleştirmek için, projenin [Özellik Sayfaları](../build/reference/property-pages-visual-cpp.md) iletişim kutusunun C/C++ klasöründe Kod Oluşturma sayfasında C++ Özel Durumlarını Etkinleştir'i seçin veya [/EHsc](../build/reference/eh-exception-handling-model.md) derleyici seçeneğini kullanın.

Bu makalede aşağıdaki konular ele:

- [Özel durumların ne zaman kullanılacağı](#_core_when_to_use_exceptions)

- [MFC özel durum desteği](#_core_mfc_exception_support)

- [Özel durumlar hakkında daha fazla okuma](#_core_further_reading_about_exceptions)

## <a name="when-to-use-exceptions"></a><a name="_core_when_to_use_exceptions"></a>Özel Durumlar Ne Zaman Kullanılır?

Program yürütme sırasında bir işlev çağrıldığında üç sonuç kategorisi oluşabilir: normal yürütme, hatalı yürütme veya anormal yürütme. Her kategori aşağıda açıklanmıştır.

- Normal yürütme

   İşlev normal şekilde çalıştırılabilir ve geri dönebilir. Bazı işlevler, işlevin sonucunu gösteren bir sonuç kodunu arayana döndürer. Olası sonuç kodları işlev için kesinlikle tanımlanır ve işlevin olası sonuçlarının aralığını temsil eder. Sonuç kodu başarı veya başarısızlığı gösterebilir veya hatta normal beklenti aralığında belirli bir hata türünü gösterebilir. Örneğin, bir dosya durumu işlevi, dosyanın var olmadığını belirten bir kod döndürebilir. Sonuç kodu beklenen birçok sonuçtan birini temsil ettiği için "hata kodu" teriminin kullanılmadığını unutmayın.

- Hatalı infaz

   Arayan, bağımsız değişkenleri işleve aktarırveya işlevi uygunsuz bir bağlamda çağırır. Bu durum bir hataya neden olur ve program geliştirme sırasında bir iddia tarafından algılanmalıdır. (İddialar hakkında daha fazla bilgi için [Bkz. C/C++ İddiaları](/visualstudio/debugger/c-cpp-assertions).)

- Anormal yürütme

   Anormal yürütme, düşük bellek veya G/Ç hataları gibi programın denetimi dışındaki koşulların işlevin sonucunu etkilediği durumları içerir. Anormal durumlar yakalayarak ve özel durumlar atılarak ele alınmalıdır.

Özel durumlar kullanmak özellikle anormal yürütme için uygundur.

## <a name="mfc-exception-support"></a><a name="_core_mfc_exception_support"></a>MFC Özel Durum Desteği

İster Doğrudan C++ özel durumlarını kullanın ister MFC özel durum makrolarını `CException`kullanın, [cexception class](../mfc/reference/cexception-class.md) veya çerçeve veya uygulamanız tarafından atılabilecek türetilmiş nesneleri kullanırsınız.

Aşağıdaki tablo, MFC tarafından sağlanan önceden tanımlanmış özel durumları gösterir.

|Özel durum sınıfı|Anlamı|
|---------------------|-------------|
|[CMemoryException Sınıfı](../mfc/reference/cmemoryexception-class.md)|Bellek dışı|
|[CFileException Sınıfı](../mfc/reference/cfileexception-class.md)|Dosya özel durumu|
|[CArchiveException Sınıfı](../mfc/reference/carchiveexception-class.md)|Arşiv/Serileştirme özel durumu|
|[CNotSupportedException Sınıfı](../mfc/reference/cnotsupportedexception-class.md)|Desteklenmeyen hizmet isteğine yanıt|
|[CResourceException Sınıf](../mfc/reference/cresourceexception-class.md)|Windows kaynak ayırma özel durumu|
|[CDaoException Sınıfı](../mfc/reference/cdaoexception-class.md)|Veritabanı özel durumları (DAO sınıfları)|
|[CDBException Sınıf](../mfc/reference/cdbexception-class.md)|Veritabanı özel durumları (ODBC sınıfları)|
|[COleException Sınıfı](../mfc/reference/coleexception-class.md)|OLE özel durumları|
|[COleDispatchException Sınıf](../mfc/reference/coledispatchexception-class.md)|Sevk (otomasyon) özel durumları|
|[CUserException Sınıf](../mfc/reference/cuserexception-class.md)|Kullanıcıyı bir ileti kutusuyla uyaran, ardından genel bir [CException Sınıfı](../mfc/reference/cexception-class.md) atan özel durum|

Sürüm 3.0'dan bu yana, MFC C++ özel durumları kullanmış, ancak yine de formdaki C++ özel durumlarına benzer olan eski özel durum işleme makrolarını desteklemektedir. Bu makrolar yeni programlama için önerilmese de, yine de geriye dönük uyumluluk için desteklenir. Makroları zaten kullanan programlarda C++ özel durumlarını da serbestçe kullanabilirsiniz. Ön işleme sırasında makrolar, Visual C++ sürüm 2.0 itibariyle C++ dilinin MSVC uygulamasında tanımlanan özel durum işleme anahtar kelimelerini değerlendirir. C++ özel durumlarını kullanmaya başlarken varolan özel durum makrolarını yerinde bırakabilirsiniz. Makroları karıştırma ve C++ özel durum işleme ve eski kodu yeni mekanizmayı kullanmak üzere dönüştürme hakkında bilgi için, [özel durumlar makalesine bakın: MFC Makroları ve C++ Özel Durumları](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) ve Özel Durumları [Kullanma: MFC Özel Durum Makrolarından Dönüştürme.](../mfc/exceptions-converting-from-mfc-exception-macros.md) Eski MFC özel durum makrolarını hala kullanmaya devam ediyorsanız, C++ özel durum anahtar sözcüklerini değerlendirin. Bkz. [Özel Durumlar: Sürüm 3.0'daki Özel Durum Makrolarında Yapılan Değişiklikler](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md). MFC, [Yapılandırılmış Özel Durum İşleme'de](/windows/win32/debug/structured-exception-handling)açıklandığı gibi Windows NT yapılandırılmış özel durum işleyicilerini (SEH) doğrudan desteklemez.

## <a name="further-reading-about-exceptions"></a><a name="_core_further_reading_about_exceptions"></a>İstisnalar Hakkında Daha Fazla Okuma

Aşağıdaki makaleler, özel durum teslimi için MFC kitaplığını kullanarak açıklayınız:

- [Özel Durumlar: Özel Durumları Yakalama ve Silme](../mfc/exceptions-catching-and-deleting-exceptions.md)

- [Özel Durumlar: Özel Durum İçeriklerini İnceleme](../mfc/exceptions-examining-exception-contents.md)

- [Özel Durumlar: Özel Durumlarda Nesneleri Serbest Bırakma](../mfc/exceptions-freeing-objects-in-exceptions.md)

- [Özel Durumlar: Kendi İşlevlerinizden Özel Durum Atma](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)

- [Özel durumlar: Veritabanı Özel Durumları](../mfc/exceptions-database-exceptions.md)

- [Özel durumlar: OLE Özel Durumları](../mfc/exceptions-ole-exceptions.md)

Aşağıdaki makaleler MFC özel durum makrolarını C++ özel durum anahtar kelimeleriyle karşılaştırır ve kodunuzu nasıl uyarlayabileceğinizi açıklar:

- [Özel Durumlar: Sürüm 3.0'da Özel Durum Makrolarındaki Değişiklikler](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)

- [Özel Durumlar: MFC Özel Durum Makrolarından Dönüştürme](../mfc/exceptions-converting-from-mfc-exception-macros.md)

- [Özel Durumlar: MFC Makroları ve C++ Özel Durumlarını Kullanma](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)

## <a name="see-also"></a>Ayrıca bkz.

[Özel durumlar ve hata işleme için modern C++ en iyi uygulamaları](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Nasıl Yaparım: Kendi Özel Özel Durum Sınıflarımı Oluşturun](https://go.microsoft.com/fwlink/p/?linkid=128045)
