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
ms.openlocfilehash: 65db0889b36cafa4b3942b7834229d1a7d9f5783
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010366"
---
# <a name="unicode-programming-summary"></a>Unicode Programlama Özeti
Unicode MFC ve C çalışma zamanı desteği avantajlarından yararlanmak için gerekir:  
  
-   Tanımlama `_UNICODE`.  
  
     Sembolünü tanımlayın `_UNICODE` programınızı derlemeden önce.  
  
-   Giriş noktası belirtin.  
  
     Üzerinde **çıkış** sayfasının **bağlayıcı** proje klasöründe [özellik sayfaları](../ide/property-pages-visual-cpp.md) iletişim kutusu, kümesi **giriş noktası** sembole`wWinMainCRTStartup`.  
  
-   Taşınabilir çalışma zamanı işlevleri ve türleri kullanır.  
  
     C çalışma zamanı işlevleri Unicode dize işleme için kullanın. Kullanabileceğiniz `wcs` ailesi işlevleri, ancak (uluslararası etkin) tam olarak taşınabilir tercih `_TCHAR` makroları. Bu makrolar tüm ön eki `_tcs`; bunlar yerine, ilişkin biri için `str` işlevler ailesini. Bu işlevler, ayrıntılı olarak açıklanan [uluslararası duruma getirme](../c-runtime-library/internationalization.md) bölümünü *çalışma zamanı kitaplığı başvurusu*. Daha fazla bilgi için [Tchar.h'de genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).  
  
     Kullanım `_TCHAR` ve açıklanan ilgili taşınabilir veri türleri [Unicode desteği](../text/support-for-unicode.md).  
  
-   Değişmez değer dizeleri düzgün bir şekilde işleyin.  
  
     Visual C++ Derleyici, bir sabit dizesi olarak kodlanmış yorumlar:  
  
    ```  
    L"this is a literal string"  
    ```  
  
     bir Unicode karakter dizesi birlikte kullanıldığı senaryolar için. Aynı öneke değişmez karakterler için kullanabilirsiniz. Kullanım `_T` değişmez değer dizeleri altında Unicode dizeleri Unicode olmayan ANSI dizelerini (MBCS dahil olmak üzere) olarak veya derleme için genel olarak, kod makrosu. Örneğin, yerine biri:  
  
    ```  
    pWnd->SetWindowText( "Hello" );  
    ```  
  
     Kullanım:  
  
    ```  
    pWnd->SetWindowText( _T("Hello") );  
    ```  
  
     İle `_UNICODE` tanımlanmış `_T` L önekli forma; sabit dizesini çevirir Aksi takdirde, `_T` L önekini olmadan çevirir.  
  
    > [!TIP]
    >  `_T` Makro aynı `_TEXT` makrosu.  
  
-   Dikkatli olun geçirme işlevleri için dize uzunluğu.  
  
     Bazı işlevler bir dizedeki karakter sayısını istediğiniz; Başkalarının bayt sayısı istersiniz. Örneğin, varsa `_UNICODE` tanımlanır, aşağıdaki çağrı bir `CArchive` nesne çalışmaz (`str` olduğu bir `CString`):  
  
    ```  
    archive.Write( str, str.GetLength( ) );    // invalid  
    ```  
  
     2 bayt genişliğinde her karakter olduğu için bir Unicode uygulamasında uzunluğu, karakter sayısı ancak değil doğru bayt sayısını sağlar. Bunun yerine, kullanmanız gerekir:  
  
    ```  
    archive.Write( str, str.GetLength( ) * sizeof( _TCHAR ) );    // valid  
    ```  
  
     hangi doğru yazılacak bayt sayısını belirtir.  
  
     Ancak, bayt odaklı yerine karakter odaklı MFC üye işlevleri bu olmadan fazladan kodlama çalışır:  
  
    ```  
    pDC->TextOut( str, str.GetLength( ) );  
    ```  
  
     `CDC::TextOut` bir karakter, bayt sayısını değil sayısını alır.  
  
-   Kullanım [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) Unicode dosyaları açmak için.  
  
 Özetlemek gerekirse, Unicode programlama için aşağıdaki desteği MFC ve çalışma zamanı kitaplığı sağlayın:  
  
-   Unicode etkin dahil olmak üzere, veritabanı sınıf üyesi işlevleri hariç tüm MFC işlevleri `CString`. `CString` Unicode/ANSI dönüştürme işlevleri de sağlar.  
  
-   Çalışma zamanı kitaplığı, tüm dize işleme işlevleri Unicode sürümlerini sağlar. (Çalışma zamanı kitaplığı aynı zamanda uygun taşınabilir sürümler Unicode veya MBCS sağlar. Bunlar `_tcs` makroları.)  
  
-   Tchar.h kaynakları taşınabilir veri türleri ve `_T` değişmez değer dizeleri ve karakterleri çevirmek için makrosu. Daha fazla bilgi için [Tchar.h'de genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).  
  
-   Çalışma Zamanı Kitaplığı bir geniş karakter sürümünü sağlayan `main`. Kullanım `wmain` uygulamanızı Unicode uyumlu hale getirmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Unicode Desteği](../text/support-for-unicode.md)