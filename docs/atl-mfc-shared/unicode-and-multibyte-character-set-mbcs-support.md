---
title: Unicode ve çok baytlı karakter kümesi (MBCS) destek | Microsoft Docs
ms.custom: ''
ms.date: 1/09/2017
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], character set support
- MBCS [C++], strings and MFC support
- strings [C++], MBCS support in MFC
- character sets [C++], multibyte
- Unicode [C++], MFC strings
- Unicode [C++], string objects
- strings [C++], Unicode
- strings [C++], character set support
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8492e4a6777e4d609e3b457cfc77d1b8a691eed3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361681"
---
# <a name="unicode-and-multibyte-character-set-mbcs-support"></a>Unicode ve çok baytlı karakter kümesi (MBCS) desteği

Örneğin, Japonca ve Çince, bazı dillerde geniş karakter kümesi vardır. Bu pazarlarında programlama desteklemek için Microsoft Foundation Class Kitaplığı (MFC) geniş karakter kümeleri işleme için iki farklı yaklaşım sağlar:

- [Unicode](#mfc-support-for-unicode-strings), `wchar_t` tabanlı uluslararası karakterler ve UTF-16 kodlanmış dize.

- [Birden çok baytlı karakter kümeleri (MBCS)](#mfc-support-for-mbcs-strings), `char` tek veya çift baytlık karakterler ve yerel ayarlara özgü karakter kümesinde kodlanmış dize.

Microsoft, tüm yeni geliştirme için MFC Unicode kitaplıkları önermiştir ve MBCS kitaplıkları, Visual Studio 2015 ve Visual Studio 2013'ün de kullanım dışı bırakılan. Bu durum artık geçerli değildir. MBCS kullanımdan kaldırma uyarıları Visual Studio 2017 kaldırılmıştır.

## <a name="mfc-support-for-unicode-strings"></a>Unicode dizeleri için MFC desteği

Tüm MFC sınıf kitaplığı koşullu Unicode karakterden ve geniş karakterler UTF-16 depolanan dizeleri için etkinleştirilir. Özellikle, sınıf [CString](../atl-mfc-shared/reference/cstringt-class.md) Unicode etkindir.

Bu kitaplık, hata ayıklayıcı ve DLL dosyaları MFC'de Unicode desteği için kullanılır:

|||||
|-|-|-|-|
|UAFXCW.LIB|UAFXCW. PDB|UAFXCWD.LIB|UAFXCWD. PDB|
|MFC*sürüm*U.LIB|MFC*sürüm*U.PDB|MFC*sürüm*U.DLL|MFC*sürüm*UD. LIB|
|MFC*sürüm*UD. PDB|MFC*sürüm*UD. DLL|MFCS*sürüm*U.LIB|MFCS*sürüm*U.PDB|
|MFCS*sürüm*UD. LIB|MFCS*sürüm*UD. PDB|MFCM*sürüm*U.LIB|MFCM*sürüm*U.PDB|
|MFCM*sürüm*U.DLL|MFCM*sürüm*UD. LIB|MFCM*sürüm*UD. PDB|MFCM*sürüm*UD. DLL|

(*sürüm* ; dosyasının sürüm numarasını temsil eder Örneğin, sürüm 14.0 '140' anlamına gelir.)

`CString` dayanır `TCHAR` veri türü. Varsa simgenin `_UNICODE` programınızın, derleme için tanımlanan `TCHAR` türü olarak tanımlanmış `wchar_t`, 16 bit karakter kodlama türü. Aksi takdirde, `TCHAR` olarak tanımlanan `char`, normal 8 bit karakter kodlaması. Bu nedenle, Unicode altında bir `CString` 16 bit karakterlerinden oluşur. Unicode türü karakterlerinden oluşur `char`.

İçin tam Unicode programlama uygulamanızın ayrıca gerekir:

- Kullanım `_T` Unicode'a taşınabilmesini koşullu kod değişmez değer dizeleri makrosuna.

- Dizeleri geçirdiğinizde olup gerektirir karakter cinsinden uzunluğu veya bayt cinsinden uzunluğu işlev bağımsız değişkenleri için dikkat edin. Fark, Unicode dizelerini kullanıyorsanız önemlidir.

- C çalışma zamanı dize işleme işlevleri taşınabilir sürümlerini kullanın.

- Aşağıdaki veri türlerini karakterleri ve karakter işaretçileri için kullanın:

   - Kullanmak `TCHAR` burada kullandığınız `char`.

   - Kullanmak `LPTSTR` burada kullandığınız `char*`.

   - Kullanmak `LPCTSTR` burada kullandığınız `const char*`. `CString` işleç sağlar `LPCTSTR` arasında dönüştürme yapma `CString` ve `LPCTSTR`.

`CString` Ayrıca Unicode algılayan Oluşturucular, atama işleçleri ve Karşılaştırma işleçleri sağlar.

[Çalışma zamanı kitaplığı başvurusu](../c-runtime-library/c-run-time-library-reference.md) taşınabilir sürümlerinde tüm dize işleme işlevleri tanımlar. Daha fazla bilgi için bkz: kategori [uluslararası hale getirme](../c-runtime-library/internationalization.md).

## <a name="mfc-support-for-mbcs-strings"></a>MBCS dizeleri için MFC desteği

Sınıf kitaplığı için birden çok baytlı karakter kümeleri de etkinleştirilir, ancak yalnızca çift bayt karakter (DBCS) ayarlar.

Birden çok baytlı karakter kümesinde bir veya iki bayt geniş karakter olabilir. Bu iki bayt genişliğinde ilk baytı özel bir "baytı" ise, yani seçilen bağlı olarak hangi kod sayfası kullanılıyor belirli bir aralıktan. Birlikte ele alındığında, sağlama ve "baytlara" benzersiz karakter kodlamasını belirleyin.

Varsa simgenin `_MBCS` türü programınızın bir yapı için tanımlanan `TCHAR`, üretileceği `CString` bağlı olduğu için eşlendiği `char`. Hangi bayt cinsinden belirlemenizi kadar olan bir `CString` ön baytlar ve baytlar olduğu. C çalışma zamanı kitaplığı bu belirlemenize yardımcı olması için işlevleri sağlar.

DBCS altında verilen bir dize tüm tek baytlı ANSI karakter, tüm çift baytlık karakterler veya iki bir birleşimini içerebilir. Bu olanakları dizeleri ayrıştırma sırasında özel dikkat gerektirir. Bu içerir `CString` nesneleri.

> [!NOTE]
> MFC'de Unicode dize serileştirme kullanmakta olduğunuz uygulamanın hangi sürümünün bakılmaksızın Unicode ve MBCS dizeleri okuyabilir. Veri dosyalarınızı programınızı Unicode ve MBCS sürümleri arasında taşınabilir.

`CString` üye işlevleri çağrıda buldukları C çalışma zamanı işlevleri özel "genel metin" sürümleri veya Unicode uyumlu işlevleri kullanın. Bu nedenle, örneğin, bir `CString` işlevi genellikle çağrısı `strcmp`, karşılık gelen genel metin işlevi çağırır `_tcscmp` yerine. Nasıl bağlı olarak simgeleri `_MBCS` ve `_UNICODE` tanımlanan `_tcscmp` gibi eşler:

|||
|-|-|
|`_MBCS` Tanımlı|`_mbscmp`|
|`_UNICODE` Tanımlı|`wcscmp`|
|Tanımlanan hiçbiri simgesi|`strcmp`|

> [!NOTE]
> Simgeler `_MBCS` ve `_UNICODE` karşılıklı olarak birbirini dışlar.

Genel metin işlev eşlemeleri tüm çalışma zamanı dize işleme yordamları açıklanmıştır [C çalışma zamanı kitaplığı başvurusu](../c-runtime-library/c-run-time-library-reference.md). Bir listesi için bkz: [uluslararası hale getirme](../c-runtime-library/internationalization.md).

Benzer şekilde, `CString` yöntemleri, genel veri türü eşlemeleri kullanılarak uygulanır. Kullanan MFC MBCS ve Unicode etkinleştirmek için `TCHAR` için `char` veya `wchar_t`, `LPTSTR` için `char*` veya `wchar_t*`, ve `LPCTSTR` için `const char*` veya `const wchar_t*`. Bunlar MBCS veya Unicode için doğru eşlemeleri emin olun.

## <a name="see-also"></a>Ayrıca Bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)  
[Dize düzenlemesi](../c-runtime-library/string-manipulation-crt.md)  
