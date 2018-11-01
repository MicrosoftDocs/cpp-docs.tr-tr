---
title: Unicode ve çok baytlı karakter kümesi (MBCS) desteği
ms.date: 1/09/2017
helpviewer_keywords:
- MFC [C++], character set support
- MBCS [C++], strings and MFC support
- strings [C++], MBCS support in MFC
- character sets [C++], multibyte
- Unicode [C++], MFC strings
- Unicode [C++], string objects
- strings [C++], Unicode
- strings [C++], character set support
ms.openlocfilehash: 8a7f79f9a75c2be4ee855d89b47b6b8e59a67d15
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596657"
---
# <a name="unicode-and-multibyte-character-set-mbcs-support"></a>Unicode ve çok baytlı karakter kümesi (MBCS) desteği

Bazı diller, örneğin, Japonca ve Çince, geniş karakter kümesi vardır. Bu pazarlar için programlamayı desteklemek için Microsoft Foundation Class Kitaplığı'nı (MFC) geniş karakter kümesi işleme için iki farklı yaklaşım sağlar:

- [Unicode](#mfc-support-for-unicode-strings), `wchar_t` geniş karakter ve UTF-16 olarak kodlanmış dize.

- [Çok baytlı karakter kümeleri (MBCS)](#mfc-support-for-mbcs-strings), **char** tek veya çift baytlı karakterlerin ve dizelerin bir yerel ayara özgü karakter kümesinden kodlanmış bağlı.

Microsoft, tüm yeni geliştirme projeleri için MFC Unicode kitaplıkları önerilir ve MBCS kitaplıkları, Visual Studio 2015 ve Visual Studio 2013'ün de kullanım dışı bırakıldı. Bu durum artık geçerli değildir. MBCS kullanımdan kaldırma uyarıları, Visual Studio 2017'de kaldırılmıştır.

## <a name="mfc-support-for-unicode-strings"></a>Unicode dizeleri için MFC desteği

Tüm MFC sınıf kitaplığı, Unicode karakter ve geniş karakter UTF-16 depolanan dizeleri için koşullu olarak etkinleştirilir. Özellikle, sınıf [CString](../atl-mfc-shared/reference/cstringt-class.md) Unicode'u destekler.

Bu kitaplık, hata ayıklayıcı ve DLL dosyaları MFC'de Unicode desteklemek için kullanılır:

|||||
|-|-|-|-|
|UAFXCW.LIB|UAFXCW. PDB|UAFXCWD.LIB|UAFXCWD. PDB|
|MFC*sürüm*U.LIB|MFC*sürüm*U.PDB|MFC*sürüm*U.DLL|MFC*sürüm*UD. LIB|
|MFC*sürüm*UD. PDB|MFC*sürüm*UD. DLL|MFCS*sürüm*U.LIB|MFCS*sürüm*U.PDB|
|MFCS*sürüm*UD. LIB|MFCS*sürüm*UD. PDB|MFCM*sürüm*U.LIB|MFCM*sürüm*U.PDB|
|MFCM*sürüm*U.DLL|MFCM*sürüm*UD. LIB|MFCM*sürüm*UD. PDB|MFCM*sürüm*UD. DLL|

(*sürüm* ; dosyasının sürüm numarasını temsil eder. Örneğin, sürüm 14.0 '140' anlamına gelir.)

`CString` TCHAR veri türüne bağlıdır. _UNICODE programınızın bir yapı için tanımlanan, TCHAR türü olarak tanımlanmış `wchar_t`, 16 bitlik bir karakter kodlama türü. Aksi takdirde olarak TCHAR tanımlanır **char**, normal 8-bit karakter kodlaması. Bu nedenle Unicode altında bir `CString` 16-bit karakterlerinden oluşur. Unicode türü karakterlerinden oluşur **char**.

İçin tam Unicode programlama, uygulamanızın da yapmanız gerekir:

- _T makro koşullu olarak kod değişmez değer dizeleri Unicode için taşınabilir olması için kullanın.

- Dizeleri başarıyla sonuçlandıktan sonra işlev bağımsız değişkenleri bir uzunluk karakter veya bayt cinsinden uzunluğu gereksiniminiz olup için dikkat edin. Fark, Unicode dizelerini kullanıyorsanız önemlidir.

- C çalışma zamanı dize işleme işlevleri taşınabilir sürümlerini kullanın.

- Aşağıdaki veri türleri, karakterleri ve karakter işaretçiler için kullanın:

   - Burada kullandığınız TCHAR kullanın **char**.

   - Burada kullandığınız LPTSTR kullanın **char**<strong>\*</strong>.

   - Burada kullandığınız LPCTSTR kullanın **const char**<strong>\*</strong>. `CString` işleç arasında dönüştürmek için LPCTSTR sağlar `CString` ve LPCTSTR.

`CString` Ayrıca, Unicode uyumlu Oluşturucular, atama işleçleri ve Karşılaştırma işleçleri sağlar.

[Çalışma zamanı kitaplığı başvurusu](../c-runtime-library/c-run-time-library-reference.md) taşınabilir sürümleri tüm dize işleme işlevleri tanımlar. Daha fazla bilgi için bkz: kategori [uluslararası duruma getirme](../c-runtime-library/internationalization.md).

## <a name="mfc-support-for-mbcs-strings"></a>MBCS dizeleri için MFC desteği

Sınıf kitaplığının çok baytlı karakter kümesi için de etkinleştirilir, ancak yalnızca çift baytlı karakter (DBCS) ayarlar.

Bir çok baytlı karakter kümesindeki bir veya iki bayt genişliğinde karakter olabilir. Bu iki bayt genişliğinde, ilk bayt özel bir "ön baytı" ise, yani seçilen bağlı olarak hangi kod sayfası kullanımda olan belirli bir aralıktan. Birlikte ele alındığında sağlama ve "baytlara" benzersiz karakter kodlaması belirtin.

_MBCS simgesini programınızın bir yapı için tanımlanan, TCHAR, üzerinde çalışamazsa `CString` bağlı olduğu için eşlenen **char**. Size hangi bayt cinsinden belirlemek için olan bir `CString` ön bayt ve baytlar olduğu. C çalışma zamanı kitaplığı, bu belirlemenize yardımcı olması için işlevleri sağlar.

DBCS altında belirli bir dize tüm tek baytlık ANSI karakterler, tüm çift baytlık karakterler veya iki bir birleşimini içerebilir. Bu olasılıklar, dizeleri ayrıştırma özel dikkat gerektirir. Bu içerir `CString` nesneleri.

> [!NOTE]
> MFC'de Unicode dize serileştirmeyi Unicode ve MBCS dizeleri çalıştırmakta olduğunuz uygulamanın hangi sürümünün bağımsız olarak okuyabilir. Veri dosyalarınızı programınızı Unicode ve MBCS sürümleri arasında taşınabilir.

`CString` üye işlevleri, çağrı C çalışma zamanı işlevleri özel "genel metin" sürümlerini veya bunlar Unicode duyarlı işlevleri kullanın. Bu nedenle, örneğin, bir `CString` işlevi genellikle çağırın `strcmp`, karşılık gelen genel metin işlevi çağıran `_tcscmp` yerine. _UNICODE ve _MBCS sembolleri nasıl tanımlandığını, bağlı olarak `_tcscmp` şu şekilde eşlenir:

|||
|-|-|
|_MBCS tanımlanmış|`_mbscmp`|
|_UNICODE tanımlanmış|`wcscmp`|
|Hiçbiri sembolü ile derlenir|`strcmp`|

> [!NOTE]
> _UNICODE ve _MBCS sembolleri birbirini dışlar.

Genel metin işlevini eşlemeleri tüm çalışma zamanı dize işleme rutinleri için açıklanmıştır [C çalışma zamanı kitaplığı başvurusu](../c-runtime-library/c-run-time-library-reference.md). Bir liste için bkz. [uluslararası duruma getirme](../c-runtime-library/internationalization.md).

Benzer şekilde, `CString` yöntemleri, genel veri türü eşlemeleri kullanılarak uygulanır. MFC MBCS ve Unicode hem etkinleştirmek için TCHAR için kullandığı **char** veya `wchar_t`, LPTSTR için **char** <strong>\*</strong> veya `wchar_t*`ve LPCTSTR için**const char** <strong>\*</strong> veya `const wchar_t*`. Bunlar MBCS veya Unicode için doğru eşlemeleri emin olun.

## <a name="see-also"></a>Ayrıca Bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Dize düzenlemesi](../c-runtime-library/string-manipulation-crt.md)
