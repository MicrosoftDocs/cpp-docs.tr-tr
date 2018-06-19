---
title: Unicode Programlama Özeti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Unicode [C++], programming with
- Unicode [C++], MFC and C run-time functions
ms.assetid: a4c9770f-6c9c-447c-996b-980920288bed
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a378d46c517dfc0fbb5857ad54bc31f4c34287b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859683"
---
# <a name="unicode-programming-summary"></a>Unicode Programlama Özeti
MFC ve C çalışma zamanı Unicode desteği yararlanmak için aktarmanız gerekir:  
  
-   Tanımlamak **_UNICODE**.  
  
     Simgenin tanımlamak **_UNICODE** programınızı oluşturmadan önce.  
  
-   Giriş noktası belirtin.  
  
     Üzerinde **çıkış** projenin Bağlayıcı klasörünün sayfası [özellik sayfaları](../ide/property-pages-visual-cpp.md) iletişim kutusunda, giriş noktası simgesi kümesine **wWinMainCRTStartup**.  
  
-   Taşınabilir çalışma zamanı işlevleri ve türlerini kullanın.  
  
     Uygun C çalışma zamanı işlevleri Unicode dize işlemesi için kullanın. Kullanabileceğiniz **wcs** işlevleri, ancak ailesi (uluslararası etkin) tam olarak taşınabilir tercih **_TCHAR** makroları. Bu makroları tüm ile önek **_tcs**; bunlar yerine, ilişkin biri için **str** ailesi işlevlerini. Bu işlevler ayrıntılı olarak açıklanmıştır [uluslararası](../c-runtime-library/internationalization.md) bölümünü *çalışma zamanı kitaplığı başvurusu*. Daha fazla bilgi için bkz: [Tchar.h'de genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).  
  
     Kullanım **_TCHAR** ve açıklanan ilgili taşınabilir veri türleri [Unicode desteği](../text/support-for-unicode.md).  
  
-   Değişmez değer dizeleri düzgün bir şekilde işler.  
  
     Visual C++ derleyicisi sabit değerli bir dize olarak kodlanmış yorumlar:  
  
    ```  
    L"this is a literal string"  
    ```  
  
     Unicode karakter dizesi demek için. Aynı öneke için değişmez değer karakter kullanabilirsiniz. Kullanım **_T** makrosu altında Unicode dizeleri veya Unicode olmadan ANSI dizeleri (MBCS dahil) olarak derlemek için değişmez değer dizeleri genel olarak, kod. Örneğin, komutun yerine kullanılır:  
  
    ```  
    pWnd->SetWindowText( "Hello" );  
    ```  
  
     Kullanım:  
  
    ```  
    pWnd->SetWindowText( _T("Hello") );  
    ```  
  
     İle **_UNICODE** tanımlanan **_T** L önekli biçimde; değişmez değer dize çevirir Aksi halde, **_T** L öneki olmadan çevirir.  
  
    > [!TIP]
    >  **_T** makrosu aynıdır `_TEXT` makrosu.  
  
-   Dikkatli olun dize uzunluklarını işlevlere geçirirken.  
  
     Bazı işlevler bir dizedeki karakter sayısını istediğiniz; Başkalarının bayt sayısı istiyor. Örneğin, varsa **_UNICODE** tanımlanır, aşağıdaki çağrı için bir `CArchive` nesne çalışmaz (`str` olan bir `CString`):  
  
    ```  
    archive.Write( str, str.GetLength( ) );    // invalid  
    ```  
  
     Her karakteri 2 bayt genişliğinde olduğundan bir Unicode uygulamasında uzunluğu, karakter sayısını ancak bayt değil doğru sayıda sağlar. Bunun yerine, kullanmanız gerekir:  
  
    ```  
    archive.Write( str, str.GetLength( ) * sizeof( _TCHAR ) );    // valid  
    ```  
  
     doğru yazılacak bayt sayısını belirtir.  
  
     Ancak, bayt odaklı yerine karakter odaklı MFC üye işlevleri olmadan ekstra kodlama çalışır:  
  
    ```  
    pDC->TextOut( str, str.GetLength( ) );  
    ```  
  
     `CDC::TextOut` karakter, sayı olmayan bayt sayısını alır.  
  
-   Kullanım [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) Unicode dosyalarını açmak için.  
  
 Özetlemek için Unicode programlama için aşağıdaki Destek MFC ve çalışma zamanı kitaplığı sağlar:  
  
-   Unicode etkin dahil olmak üzere, veritabanı sınıf üyesi işlevleri dışında tüm MFC işlevleri `CString`. `CString` Ayrıca Unicode/ANSI dönüştürme işlevleri sağlar.  
  
-   Çalışma Zamanı Kitaplığı Unicode sürümleri tüm dize işleme işlevleri sağlar. (Çalışma zamanı kitaplığı da uygun taşınabilir sürümler Unicode veya MBCS sağlar. Bunlar **_tcs** makroları.)  
  
-   Tchar.h sağlayan taşınabilir veri türleri ve **_T** değişmez değer dizeleri ve karakterleri çevirme için makrosu. Daha fazla bilgi için bkz: [Tchar.h'de genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).  
  
-   Çalışma Zamanı Kitaplığı bir joker karakter sürümünü sağlayan **ana**. Kullanım **wmain** uygulamanızı Unicode uyumlu yapma.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Unicode Desteği](../text/support-for-unicode.md)