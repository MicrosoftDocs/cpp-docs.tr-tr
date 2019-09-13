---
title: Unicode ve çok baytlı karakter kümesi (MBCS) desteği
ms.date: 01/09/2017
helpviewer_keywords:
- MFC [C++], character set support
- MBCS [C++], strings and MFC support
- strings [C++], MBCS support in MFC
- character sets [C++], multibyte
- Unicode [C++], MFC strings
- Unicode [C++], string objects
- strings [C++], Unicode
- strings [C++], character set support
ms.openlocfilehash: 983b3d9bc72d99ab3c665f86cffd205dccf873e8
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927900"
---
# <a name="unicode-and-multibyte-character-set-mbcs-support"></a>Unicode ve çok baytlı karakter kümesi (MBCS) desteği

Örneğin, Japonca ve Çince gibi bazı dillerin büyük karakter kümeleri vardır. Bu pazarlar için programlamayı desteklemek amacıyla, Microsoft Foundation Class Kitaplığı (MFC) büyük karakter kümelerini işlemek için iki farklı yaklaşım sağlar:

- [Unicode](#mfc-support-for-unicode-strings), `wchar_t` tabanlı geniş karakterler ve UTF-16 olarak kodlanmış dizeler.

- [Çok baytlı karakter kümeleri (MBCS)](#mfc-support-for-mbcs-strings), **karakter** tabanlı tek veya çift baytlık karakterler ve dizeler, yerel ayara özgü karakter kümesi içinde kodlandı.

Microsoft tüm yeni geliştirmelerde MFC Unicode kitaplıklarını önermiştir ve Visual Studio 2013 ve Visual Studio 2015 ' de MBCS kitaplıkları kullanım dışıdır. Bu durum artık geçerli değildir. Visual Studio 2017 ' de MBCS kullanımdan kaldırma uyarıları kaldırılmıştır.

## <a name="mfc-support-for-unicode-strings"></a>Unicode dizeleri için MFC desteği

Tüm MFC sınıf kitaplığı, UTF-16 olarak geniş karakterlerle depolanan Unicode karakterler ve dizeler için koşullu olarak etkinleştirilmiştir. Özellikle, Class [CString](../atl-mfc-shared/reference/cstringt-class.md) Unicode etkindir.

Bu kitaplık, hata ayıklayıcı ve DLL dosyaları MFC 'de Unicode 'U desteklemek için kullanılır:

|||||
|-|-|-|-|
|UAFXCW.LIB|UAFXCW.PDB|UAFXCWD.LIB|UAFXCWD.PDB|
|MFC*Sürüm*U. LIB|MFC*Sürüm*U. pdb|MFC*Sürüm*U. dll|MFC*Sürüm*ud 'si. LıB|
|MFC*Sürüm*ud 'si. PDB|MFC*Sürüm*ud 'si. DOSYASıNı|MFCS*Sürüm*U. LIB|MFCS*Sürüm*U. pdb|
|MFCS*Sürüm*ud. LıB|MFCS*Sürüm*ud. PDB|MFCM*Sürüm*U. LIB|MFCM*Sürüm*U. pdb|
|MFCM*Sürüm*U. dll|MFCM*Sürüm*ud. LıB|MFCM*Sürüm*ud. PDB|MFCM*Sürüm*ud. DOSYASıNı|

(*Sürüm* , dosyanın sürüm numarasını temsil eder; örneğin, ' 140 ', sürüm 14,0 anlamına gelir.)

`CString`, TCHAR veri türünü temel alır. Symbol _UNICODE, programınızın bir derlemesi için tanımlandıysa, tchar türü `wchar_t`, 16 bitlik bir karakter kodlama türü olarak tanımlanır. Aksi halde TCHAR, normal 8 bit karakter kodlaması olan **char**olarak tanımlanır. Bu nedenle, Unicode altında a `CString` 16 bit karakterden oluşur. Unicode olmadan, **char**türünde karakterlerden oluşur.

Uygulamanızın Unicode programlamayı tamamlamaya yönelik olarak, şunları da yapmanız gerekir:

- Unicode 'a taşınabilir olacak değişmez dizeleri koşullu olarak kodlarda, _T makrosunu kullanın.

- Dizeleri geçirdiğinizde, işlev bağımsız değişkenlerinin karakter uzunluğunda veya bayt cinsinden bir uzunluğa ihtiyacı olup olmadığına dikkat edin. Unicode dizeleri kullanıyorsanız, fark önemlidir.

- C çalışma zamanı dize işleme işlevlerinin taşınabilir sürümlerini kullanın.

- Karakterler ve karakter işaretçileri için aşağıdaki veri türlerini kullanın:

   - **Char**'ı KULLANDıĞıNıZ yerde TCHAR 'ı kullanın.

   - <strong>Char\*</strong>'ı kullandığınız yerde LPTSTR kullanın.

   - **Const char**<strong>\*</strong>'ı kullanacağınız LPCTSTR kullanın. `CString`ve LPCTSTR arasında `CString` dönüştürme yapmak için LPCTSTR işlecini sağlar.

`CString`Ayrıca Unicode kullanan oluşturucular, atama işleçleri ve karşılaştırma işleçleri sağlar.

[Çalışma zamanı kitaplık başvurusu](../c-runtime-library/c-run-time-library-reference.md) , tüm dize işleme işlevlerinin taşınabilir sürümlerini tanımlar. Daha fazla bilgi için bkz. Kategori [Uluslararası duruma getirme](../c-runtime-library/internationalization.md).

## <a name="mfc-support-for-mbcs-strings"></a>MBCS dizeleri için MFC desteği

Sınıf kitaplığı aynı zamanda çok baytlı karakter kümeleri için de etkinleştirilir, ancak yalnızca çift baytlı karakter kümeleri için (DBCS).

Çok baytlı bir karakter kümesinde bir karakter bir veya iki bayt genişliğinde olabilir. İki baytlık bir genişse, ilk baytı, hangi kod sayfasının kullanımda olduğuna bağlı olarak belirli bir aralıktan seçilen özel bir "ön bayt" olur. Birlikte alınan, lider ve "iz baytları" benzersiz bir karakter kodlaması belirtir.

Programınızın bir derlemesi için bir yazım türü tanımlanırsa, üzerine `CString` taban, **char**ile eşlenir yazın. Bir `CString` içinde hangi baytların ön bayt olduğunu ve bu baytların iz bayt olduğunu belirlemektir. C çalışma zamanı kitaplığı, bunu belirlemenize yardımcı olmak için işlevler sağlar.

DBCS altında, belirli bir dize tüm tek baytlı ANSI karakterlerini, tüm çift baytlı karakterleri veya ikisinin birleşimini içerebilir. Bu olasılıklar, dizeleri ayrıştırırken özel bir ilgilenmesini gerektirir. Bu nesneleri `CString` içerir.

> [!NOTE]
> MFC 'de Unicode dize serileştirme, çalıştırdığınız uygulamanın hangi sürümünden bağımsız olarak hem Unicode hem de MBCS dizelerini okuyabilir. Veri dosyalarınız, programınızın Unicode ve MBCS sürümleri arasında taşınabilir.

`CString`üye işlevleri, çağırdıkları C çalışma zamanı işlevlerinin özel "genel metin" sürümlerini kullanır veya Unicode kullanan işlevleri kullanır. Bu nedenle, örneğin, bir `CString` işlev genellikle çağrıyorsa `strcmp`, bunun yerine karşılık gelen genel metin işlevini `_tcscmp` çağırır. _MBCS ve _UNICODE 'un nasıl tanımlandığına bağlı olarak, `_tcscmp` aşağıdaki gibi haritalar:

|||
|-|-|
|_MBCS tanımlanmış|`_mbscmp`|
|_UNICODE tanımlanmış|`wcscmp`|
|Sembol tanımlı değil|`strcmp`|

> [!NOTE]
> _MBCS ve _UNıCODE sembolleri birbirini dışlıyor.

Tüm çalışma zamanı dize işleme yordamlarının genel metin işlev eşlemeleri [C çalışma zamanı kitaplığı başvurusunda](../c-runtime-library/c-run-time-library-reference.md)ele alınmıştır. Bir liste için bkz. [Uluslararası duruma getirme](../c-runtime-library/internationalization.md).

Benzer şekilde `CString` , yöntemler genel veri türü eşlemeleri kullanılarak uygulanır. Hem MBCS hem de UNICODE 'u etkinleştirmek için MFC **char** `wchar_t`için Tchar, **char** <strong>\*</strong> `wchar_t*`veya için LPTSTR, **const char** <strong>\*</strong> `const wchar_t*`için de LPCTSTR kullanır. Bu, MBCS veya Unicode için doğru eşlemeleri güvence altına aldığından emin olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Dize düzenleme](../c-runtime-library/string-manipulation-crt.md)
