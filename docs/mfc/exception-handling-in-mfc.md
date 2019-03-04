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
ms.openlocfilehash: cb11a74932e44f94f481a2fdc48b8d6ee359f9e8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260549"
---
# <a name="exception-handling-in-mfc"></a>MFC'de Özel Durum İşleme

Bu makalede MFC'de özel durum işleme mekanizmalarını açıklar. İki mekanizma vardır:

- C++ özel durumlarını, MFC sürüm 3.0 kullanılabilir ve üzeri

- MFC özel durum makroları, MFC sürüm 1.0 ve üzeri

MFC kullanarak yeni bir uygulama yazıyorsanız, C++ mekanizmasını kullanmanız gerekir. Mevcut uygulamanızı zaten bu mekanizması yaygın olarak kullanan makrosu tabanlı mekanizma kullanabilirsiniz.

C++ özel durumlarını yerine MFC özel durum makroları kullanmak için mevcut kodu kolayca dönüştürebilirsiniz. Bunu yapmak için yönergeleri ve kod dönüştürme avantajları makalesinde açıklanan [özel durumlar: MFC özel durum makrolarından dönüştürme](../mfc/exceptions-converting-from-mfc-exception-macros.md).

MFC özel durum makroları kullanarak uygulama geliştirdiyseniz Bu makrolar, yeni kodunuzda C++ özel durumlarını kullanırken mevcut kodunuzu kullanmaya devam edebilirsiniz. Makaleyi [özel durumlar: Sürüm 3.0 özel durum makrolarındaki değişiklikler](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md) Bunu yapmak için yönergeler sağlar.

> [!NOTE]
>  C++ özel durum işleme kodunuzda etkinleştirmek için C/C++ klasörü projeye ait kod oluşturma sayfasında C++ özel durumlarını etkinleştir seçin [özellik sayfaları](../ide/property-pages-visual-cpp.md) iletişim kutusu veya kullanım [/ehsc](../build/reference/eh-exception-handling-model.md) derleyici seçeneği.

Bu makalede, aşağıdaki konular ele alınmaktadır:

- [Özel durumlar kullanma zamanı](#_core_when_to_use_exceptions)

- [MFC özel durum desteği](#_core_mfc_exception_support)

- [Özel durumları hakkında daha fazla bilgi](#_core_further_reading_about_exceptions)

##  <a name="_core_when_to_use_exceptions"></a> Özel durumlar kullanma zamanı

Program yürütülmesi sırasında bir işlev çağrıldığında sonuçlarını üç kategorisi oluşabilir: normal yürütmenin, hatalı yürütme veya anormal yürütme. Her kategori aşağıda açıklanmıştır.

- Normal yürütmenin

   İşlev, normalde yürütün ve dönüş. Bazı işlevler bir sonuç kodu işlev sonucunu gösteren çağırana döndürür. Olası sonuç kodları işlevi kesin olarak tanımlanır ve sonuçtan işlevin aralığını temsil eder. Sonuç kodu, başarı veya başarısızlık belirtebilir veya bile beklentileri normal aralığında ise hata belirli bir tür belirtebilirsiniz. Örneğin, bir dosya durumu işlevi dosya yok gösteren bir kod iade edebilirsiniz. Sonuç kodu birçok beklenen sonuçlar göstermesi "hata kodu" terimi kullanılmaz unutmayın.

- Hatalı yürütme

   Çağıran işleve bağımsız değişkenleri geçirme içinde bazı hata yapar veya uygun olmayan bir bağlamda işlevini çağırır. Bu durum bir hataya neden olur ve program geliştirme sırasında onaylama algılanmalıdır. (Onaylar hakkında daha fazla bilgi için bkz. [C/C++ onaylamaları](/visualstudio/debugger/c-cpp-assertions).)

- Olağan dışı yürütme

   Olağan dışı yürütme, düşük bellek veya g/ç hataları gibi programın denetimin dışında kalan koşullar işlev sonucunu burada etkileyen durumlarda içerir. Anormal durumları yakalama ve özel durumları atma yapılması gerekir.

Özel durumlar kullanma, anormal yürütme için özellikle uygundur.

##  <a name="_core_mfc_exception_support"></a> MFC özel durum desteği

C++ özel durumlarını doğrudan kullanın ya da MFC özel durum makroları kullanmak isteyip kullanacağınız [CException sınıfı](../mfc/reference/cexception-class.md) veya `CException`-türetilmiş framework tarafından veya uygulamanız tarafından oluşturulan nesneleri.

MFC tarafından sağlanan önceden tanımlanmış özel durumlar aşağıdaki tabloda gösterilmektedir.

|Özel durum sınıfı|Açıklama|
|---------------------|-------------|
|[CMemoryException Sınıfı](../mfc/reference/cmemoryexception-class.md)|Bellek yetersiz|
|[CFileException Sınıfı](../mfc/reference/cfileexception-class.md)|Dosya özel durumu|
|[CArchiveException Sınıfı](../mfc/reference/carchiveexception-class.md)|Arşiv/seri hale getirme özel durumu|
|[CNotSupportedException Sınıfı](../mfc/reference/cnotsupportedexception-class.md)|Yanıt için desteklenmeyen hizmet istemek için|
|[CResourceException Sınıfı](../mfc/reference/cresourceexception-class.md)|Windows kaynak ayırma özel durumu|
|[CDaoException Sınıfı](../mfc/reference/cdaoexception-class.md)|Veritabanı özel durumları (DAO sınıfları)|
|[CDBException Sınıfı](../mfc/reference/cdbexception-class.md)|Veritabanı özel durumları (ODBC sınıfları)|
|[COleException Sınıfı](../mfc/reference/coleexception-class.md)|OLE özel durumları|
|[COleDispatchException Sınıfı](../mfc/reference/coledispatchexception-class.md)|Gönderme (Otomasyon) özel durumları|
|[CUserException Sınıfı](../mfc/reference/cuserexception-class.md)|Uyaran bir ileti kutusu ile kullanıcı ardından Exception'a genel [CException sınıfı](../mfc/reference/cexception-class.md)|

> [!NOTE]
>  MFC, C++ özel durumlarını hem MFC özel durum makroları destekler. MFC doğrudan desteklemez Windows NT yapılandırılmış özel durum işleyicileri (SEH) bölümünde açıklandığı gibi [yapılandırılmış özel durum işleme](/windows/desktop/debug/structured-exception-handling).

##  <a name="_core_further_reading_about_exceptions"></a> Özel durumları hakkında daha fazla okuma

Aşağıdaki makaleler, özel durum teslim etme için MFC Kitaplığı'nı kullanarak açıklar:

- [Özel durumlar: Yakalama ve özel durumları silme](../mfc/exceptions-catching-and-deleting-exceptions.md)

- [Özel durumlar: Özel durum içeriklerini İnceleme](../mfc/exceptions-examining-exception-contents.md)

- [Özel durumlar: Özel durumlarda nesneleri serbest bırakma](../mfc/exceptions-freeing-objects-in-exceptions.md)

- [Özel durumlar: Kendi İşlevlerinizden özel durumları atma](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)

- [Özel durumlar: Veritabanı özel durumları](../mfc/exceptions-database-exceptions.md)

- [Özel durumlar: OLE özel durumları](../mfc/exceptions-ole-exceptions.md)

Aşağıdaki makaleler, C++ özel durum anahtar sözcüklerini MFC özel durum makroları karşılaştırın ve kodunuzu nasıl uyarlayabileceğiniz açıklanmaktadır:

- [Özel durumlar: Sürüm 3.0 özel durum makrolarındaki değişiklikler](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)

- [Özel durumlar: MFC özel durum makrolarından dönüştürme](../mfc/exceptions-converting-from-mfc-exception-macros.md)

- [Özel durumlar: MFC makroları ve C++ özel durumlarını kullanma](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ Özel Durum İşleme](../cpp/cpp-exception-handling.md)<br/>
[Nasıl Yaparım Kendi özel durum sınıfları oluşturma](http://go.microsoft.com/fwlink/p/?linkid=128045)
