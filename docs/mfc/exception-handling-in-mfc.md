---
description: "Daha fazla bilgi edinin: MFC 'de özel durum Işleme"
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
ms.openlocfilehash: 097f2bf635526769253ef81d5381be82605ab118
ms.sourcegitcommit: 6183207b11575d7b44ebd7c18918e916a0d8c63d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97951560"
---
# <a name="exception-handling-in-mfc"></a>MFC'de Özel Durum İşleme

Bu makalede, MFC 'de kullanılabilen özel durum işleme mekanizmaları açıklanmaktadır. İki mekanizma vardır:

- C++ özel durumları, MFC sürüm 3,0 ve üzeri sürümlerde kullanılabilir

- MFC özel durum makroları, 1,0 ve üzeri MFC sürümlerinde kullanılabilir

MFC kullanarak yeni bir uygulama yazıyorsanız, C++ mekanizmasını kullanmanız gerekir. Mevcut uygulamanız zaten bu mekanizmayı yaygın olarak kullanıyorsa, makro tabanlı mekanizmayı kullanabilirsiniz.

Mevcut kodu MFC özel durum makroları yerine C++ özel durumlarını kullanacak şekilde kolayca dönüştürebilirsiniz. Kodunuzu ve yönergeleri dönüştürmenin avantajları, [özel durumlar: MFC özel durum makrolarından dönüştürme](exceptions-converting-from-mfc-exception-macros.md)konusunda açıklanmaktadır.

MFC özel durum makrolarını kullanarak zaten bir uygulama geliştirdiyseniz, mevcut kodunuzda bu makroları kullanmaya devam edebilirsiniz, ancak yeni kodunuzda C++ özel durumlarını kullanıyorsunuz. Makale [özel durumları: sürüm 3,0 ' deki özel durum Makrolarındaki Değişiklikler](exceptions-changes-to-exception-macros-in-version-3-0.md) bu işlemi gerçekleştirmek için yönergeler sağlar.

> [!NOTE]
> Kodunuzda C++ özel durum işlemeyi etkinleştirmek için, projenin [Özellik sayfaları](../build/reference/property-pages-visual-cpp.md) Iletişim kutusunun C/C++ klasöründe bulunan kod üretimi sayfasında C++ özel durumlarını etkinleştir ' i seçin veya [/EHsc](../build/reference/eh-exception-handling-model.md) derleyici seçeneğini kullanın.

Bu makalede aşağıdaki konular ele alınmaktadır:

- [Özel durumlar ne zaman kullanılır?](#_core_when_to_use_exceptions)

- [MFC özel durum desteği](#_core_mfc_exception_support)

- [Özel durumlar hakkında daha fazla bilgi](#_core_further_reading_about_exceptions)

## <a name="when-to-use-exceptions"></a><a name="_core_when_to_use_exceptions"></a> Özel durumlar ne zaman kullanılır?

Program yürütme sırasında bir işlev çağrıldığında üç sonuç kategorisi oluşabilir: normal yürütme, hatalı yürütme veya olağan dışı yürütme. Her kategori aşağıda açıklanmıştır.

- Normal yürütme

   İşlev normal çalışabilir ve döndürebilir. Bazı işlevler, çağrı için işlevin sonucunu gösteren bir sonuç kodu döndürür. Olası sonuç kodları işlev için kesin olarak tanımlanmıştır ve işlevin olası sonuçlarının aralığını temsil eder. Sonuç kodu, başarılı veya başarısız olduğunu belirtebilir, hatta normal beklentiler aralığında olan belirli bir hata türünü gösterebilir. Örneğin, bir dosya durumu işlevi, dosyanın mevcut olmadığını belirten bir kod döndürebilir. Bir sonuç kodu beklenen birçok sonuçlardan birini temsil ettiğinden "hata kodu" teriminin kullanılmadığını unutmayın.

- Hatalı yürütme

   Çağıran, işleve bağımsız değişken geçirmeli veya işlevi uygunsuz bir bağlamda çağıran bir hata oluşturur. Bu durum bir hataya neden olur ve program geliştirme sırasında bir onaylama tarafından algılanmalıdır. (Onaylamalar hakkında daha fazla bilgi için bkz. [C/C++ Onayları](/visualstudio/debugger/c-cpp-assertions).)

- Olağan dışı yürütme

   Olağan dışı yürütme, programın denetimi dışındaki koşullarda (düşük bellek veya g/ç hataları gibi) işlevin sonucunu etkili bir şekilde etkileyen durumlar içerir. Olağan dışı durumlar, özel durumlar yakalanarak ve oluşturulurken işlenmelidir.

Özel durumların kullanılması özellikle olağan dışı yürütme için uygundur.

## <a name="mfc-exception-support"></a><a name="_core_mfc_exception_support"></a> MFC özel durum desteği

C++ özel durumlarını doğrudan kullanmanıza veya MFC özel durum makrolarını kullanmanıza bakılmaksızın, çerçeve veya uygulamanız tarafından oluşturulan [CException sınıfı](reference/cexception-class.md) ya da `CException` türetilmiş nesneleri kullanırsınız.

Aşağıdaki tabloda, MFC tarafından sunulan önceden tanımlanmış özel durumlar gösterilmektedir.

|Özel durum sınıfı|Anlamı|
|---------------------|-------------|
|[CMemoryException sınıfı](reference/cmemoryexception-class.md)|Bellek yetersiz|
|[CFileException Sınıfı](reference/cfileexception-class.md)|Dosya özel durumu|
|[CArchiveException sınıfı](reference/carchiveexception-class.md)|Arşiv/serileştirme özel durumu|
|[CNotSupportedException sınıfı](reference/cnotsupportedexception-class.md)|Desteklenmeyen hizmet isteğine yanıt|
|[CResourceException sınıfı](reference/cresourceexception-class.md)|Windows kaynak ayırma özel durumu|
|[CDaoException sınıfı](reference/cdaoexception-class.md)|Veritabanı özel durumları (DAO sınıfları)|
|[CDBException sınıfı](reference/cdbexception-class.md)|Veritabanı özel durumları (ODBC sınıfları)|
|[Cotaexception sınıfı](reference/coleexception-class.md)|OLE özel durumları|
|[Cotadispatchexception sınıfı](reference/coledispatchexception-class.md)|Dağıtım (Otomasyon) özel durumları|
|[CUserException sınıfı](reference/cuserexception-class.md)|Kullanıcıyı bir ileti kutusuyla uyaran ve sonra genel bir [CException sınıfı](reference/cexception-class.md) oluşturan özel durum|

Sürüm 3,0 ' den itibaren, MFC C++ özel durumlarını kullandı, ancak form içindeki C++ özel durumlarına benzeyen eski özel durum işleme makrolarını hala destekliyor. Bu makrolar yeni programlama için önerilmese de, geriye dönük uyumluluk için hala desteklenirler. Makroları zaten kullanan programlarda, C++ özel durumlarını da ücretsiz olarak kullanabilirsiniz. Ön işleme sırasında makrolar, Visual C++ sürüm 2,0 itibariyle C++ dilinin MSVC uygulamasında tanımlanan özel durum işleme anahtar sözcüklerini değerlendirir. C++ özel durumlarını kullanmaya başladığınızda, mevcut özel durum makrolarını yerinde bırakabilirsiniz. Makroları ve C++ özel durum işlemesini karıştırma ve yeni mekanizmayı kullanmak için eski kodu dönüştürme hakkında bilgi için bkz. Makaleler [özel durumları: MFC makroları ve C++ özel](exceptions-using-mfc-macros-and-cpp-exceptions.md) durumlarını kullanma [: MFC özel durum makrolarından dönüştürme](exceptions-converting-from-mfc-exception-macros.md). Eski MFC özel durum makrolarını hala kullanmaya devam ediyorsanız, C++ özel durum anahtar sözcüklerini değerlendirin. Bkz. [özel durumlar: sürüm 3,0 ' de özel durum Makrolarındaki Değişiklikler](exceptions-changes-to-exception-macros-in-version-3-0.md). MFC, [yapılandırılmış özel durum işlemede](/windows/win32/debug/structured-exception-handling)anlatıldığı gıbı Windows NT yapılandırılmış özel durum IŞLEYICILERINI (SEH) doğrudan desteklemez.

## <a name="further-reading-about-exceptions"></a><a name="_core_further_reading_about_exceptions"></a> Özel durumlar hakkında daha fazla bilgi

Aşağıdaki makalelerde özel durum teslim etmek için MFC kitaplığı kullanımı açıklanmaktadır:

- [Özel durumlar: özel durumları yakalama ve silme](exceptions-catching-and-deleting-exceptions.md)

- [Özel durumlar: özel durum Içeriklerini Inceleme](exceptions-examining-exception-contents.md)

- [Özel durumlar: özel durumlarda nesneleri serbest bırakma](exceptions-freeing-objects-in-exceptions.md)

- [Özel durumlar: kendi Işlevlerinizden özel durumlar oluşturma](exceptions-throwing-exceptions-from-your-own-functions.md)

- [Özel durumlar: veritabanı özel durumları](exceptions-database-exceptions.md)

- [Özel durumlar: OLE özel durumları](exceptions-ole-exceptions.md)

Aşağıdaki makalelerde MFC özel durum makroları C++ özel durum anahtar sözcükleriyle karşılaştırılmaktadır ve kodunuzu nasıl uyarlayabileceğiniz açıklanmıştır:

- [Özel durumlar: sürüm 3,0 ' de özel durum Makrolarındaki Değişiklikler](exceptions-changes-to-exception-macros-in-version-3-0.md)

- [Özel durumlar: MFC özel durum makrolarından dönüştürme](exceptions-converting-from-mfc-exception-macros.md)

- [Özel durumlar: MFC makrolarını ve C++ özel durumlarını kullanma](exceptions-using-mfc-macros-and-cpp-exceptions.md)

## <a name="see-also"></a>Ayrıca bkz.

[Özel durumlar ve hata işleme için modern C++ en iyi uygulamaları](../cpp/errors-and-exception-handling-modern-cpp.md)
