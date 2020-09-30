---
title: Unicode Programlama Özeti
ms.date: 11/04/2016
helpviewer_keywords:
- Unicode [C++], programming with
- Unicode [C++], MFC and C run-time functions
ms.assetid: a4c9770f-6c9c-447c-996b-980920288bed
ms.openlocfilehash: 5095e1c58db3e5c35eb9215367f2fbb064bc228a
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504714"
---
# <a name="unicode-programming-summary"></a>Unicode Programlama Özeti

Unicode için MFC ve C çalışma zamanı desteğinin avantajlarından yararlanmak için şunlar gerekir:

- Tanımlayın `_UNICODE` .

   `_UNICODE`Programınızı yapılandırmadan önce sembolü tanımlayın.

- Giriş noktasını belirtin.

   Projenin [Özellik sayfaları](../build/reference/property-pages-visual-cpp.md) Iletişim kutusundaki **bağlayıcı** klasörünün **Gelişmiş** sayfasında, **giriş noktası** sembolünü olarak ayarlayın `wWinMainCRTStartup` .

- Taşınabilir çalışma zamanı işlevlerini ve türlerini kullanın.

   Unicode dize işleme için uygun C çalışma zamanı işlevlerini kullanın. `wcs`İşlev ailesini kullanabilirsiniz, ancak tamamen taşınabilir (Uluslararası) makroları tercih edebilirsiniz `_TCHAR` . Bu makroların tümü ön ekine sahiptir `_tcs` ; bunlar için bir tane olmak üzere `str` işlev ailesi için kullanılır. Bu işlevler, *çalışma zamanı kitaplık başvurusunun* [Uluslararası duruma getirme](../c-runtime-library/internationalization.md) bölümünde ayrıntılı olarak açıklanmıştır. Daha fazla bilgi için, bkz. [Tchar. h 'de Genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).

   `_TCHAR`Ve [Unicode desteği](../text/support-for-unicode.md)bölümünde açıklanan ilgili taşınabilir veri türlerini kullanın.

- Sabit dizeleri düzgün bir şekilde işleyin.

   Visual C++ Derleyici, şu şekilde kodlanmış bir sabit dize Yorumlar:

    ```cpp
    L"this is a literal string"
    ```

   bir Unicode karakter dizesi anlamına gelir. Sabit karakterler için aynı öneki kullanabilirsiniz. `_T`Değişmez dizeleri genelden kodlayarak, Unicode veya ANSI dizeleri (MBCS dahil) Ile Unicode olmayan bir şekilde derlemek için makroyu kullanın. Örneğin, yerine:

    ```cpp
    pWnd->SetWindowText( "Hello" );
    ```

   kullanırsınız

    ```cpp
    pWnd->SetWindowText( _T("Hello") );
    ```

   `_UNICODE`Tanımlı ile, `_T` değişmez dizeyi l önekli forma çevirir; Aksi takdirde, `_T` dizeyi l öneki olmadan çevirir.

    > [!TIP]
    >  `_T`Makro, makro ile aynıdır `_TEXT` .

- Dize uzunluklarını işlevlere geçirme konusunda dikkatli olun.

   Bazı işlevler bir dizedeki karakter sayısını istiyor; diğerleri bayt sayısını istiyor. Örneğin, `_UNICODE` tanımlanmışsa, bir nesne için aşağıdaki çağrı `CArchive` çalışmaz ( `str` bir olur `CString` ):

    ```cpp
    archive.Write( str, str.GetLength( ) );    // invalid
    ```

   Bir Unicode uygulamasında uzunluk, her karakter 2 bayt genişliğinde olduğu için karakter sayısını verir ancak doğru sayıda bayt değildir. Bunun yerine, şunu kullanmanız gerekir:

    ```cpp
    archive.Write( str, str.GetLength( ) * sizeof( _TCHAR ) );    // valid
    ```

   yazılacak doğru bayt sayısını belirtir.

   Ancak, bayt odaklı yerine karakter odaklı olan MFC üye işlevleri bu ek kodlama olmadan çalışır:

    ```cpp
    pDC->TextOut( str, str.GetLength( ) );
    ```

   `CDC::TextOut` bayt sayısı değil, birkaç karakter alır.

- Unicode dosyalarını açmak için [fopen_s _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) kullanın.

Özetlemek gerekirse, MFC ve çalışma zamanı kitaplığı, Unicode programlama için aşağıdaki desteği sağlar:

- Veritabanı sınıfı üye işlevleri hariç, tüm MFC işlevleri de dahil olmak üzere Unicode etkindir `CString` . `CString` Ayrıca Unicode/ANSI dönüştürme işlevleri de sağlar.

- Çalışma zamanı kitaplığı, tüm dize işleme işlevlerinin Unicode sürümlerini sağlar. (Çalışma zamanı kitaplığı, Unicode veya MBCS için uygun taşınabilir sürümleri de sağlar. Bunlar `_tcs` makrolardır.)

- Tchar. h, taşınabilir veri türleri ve `_T` değişmez dize ve karakterleri çevirmek için makro sağlar. Daha fazla bilgi için, bkz. [Tchar. h 'de Genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).

- Çalışma zamanı kitaplığı, öğesinin geniş karakterli bir sürümünü sağlar `main` . `wmain`Uygulamanızı Unicode 'a duyarlı hale getirmek için kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Unicode desteği](../text/support-for-unicode.md)
