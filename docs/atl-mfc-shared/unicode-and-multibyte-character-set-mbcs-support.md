---
title: Unicode ve Multibyte Karakter Seti (MBCS) Desteği
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
ms.openlocfilehash: e1b93a3540cba553afd8f133c18496bddbd561b8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317432"
---
# <a name="unicode-and-multibyte-character-set-mbcs-support"></a>Unicode ve Multibyte Karakter Seti (MBCS) Desteği

Bazı dillerde, örneğin, Japonca ve Çince, büyük karakter kümeleri vardır. Bu pazarlar için programlamayı desteklemek için, Microsoft Foundation Class Library (MFC), büyük karakter kümelerini işlemek için iki farklı yaklaşım sağlar:

- [Unicode](#mfc-support-for-unicode-strings) `wchar_t` , UTF-16 olarak kodlanmış geniş karakterler ve dizeleri tabanlı.

- [Çok bayt Karakter Kümeleri (MBCS),](#mfc-support-for-mbcs-strings) **char** tabanlı tek veya çift bayt karakter ve yerel karakter kümesinde kodlanmış dizeleri.

Microsoft, tüm yeni geliştirmeiçin MFC Unicode kitaplıklarını tavsiye etti ve Visual Studio 2013 ve Visual Studio 2015'te MBCS kitaplıkları amortismana uğradı. Bu durum artık geçerli değildir. Visual Studio 2017'de MBCS amortisman uyarıları kaldırıldı.

## <a name="mfc-support-for-unicode-strings"></a>Unicode Dizeleri için MFC Desteği

UtF-16 olarak geniş karakterlerde depolanan Unicode karakterleri ve dizeleri için tüm MFC sınıf kitaplığı koşullu olarak etkinleştirilir. Özellikle, [Sınıf CString](../atl-mfc-shared/reference/cstringt-class.md) Unicode etkindir.

Bu kitaplık, hata ayıklayıcı ve DLL dosyaları MFC'de Unicode'u desteklemek için kullanılır:

|||||
|-|-|-|-|
|UAFXCW. Lib|UAFXCW. Pdb|UAFXCWD. Lib|UAFXCWD. Pdb|
|MFC*sürümü*U.LIB|MFC*sürümü*U.PDB|MFC*sürümü*U.DLL|MFC*sürümü*UD. Lib|
|MFC*sürümü*UD. Pdb|MFC*sürümü*UD. Dll|MFCS*sürümü*U.LIB|MFCS*sürümü*U.PDB|
|MFCS*sürüm*UD. Lib|MFCS*sürüm*UD. Pdb|MFCM*sürümü*U.LIB|MFCM*sürümü*U.PDB|
|MFCM*sürümü*U.DLL|MFCM*sürüm*UD. Lib|MFCM*sürüm*UD. Pdb|MFCM*sürüm*UD. Dll|

(*sürüm* dosyanın sürüm numarasını temsil eder; örneğin, '140' sürüm 14.0 anlamına gelir.)

`CString`TCHAR veri türüne dayanır. _UNICODE sembolü, programınızın bir yapısı için tanımlanmışsa, `wchar_t`TCHAR türü , 16 bit karakter kodlama türü olarak tanımlanır. Aksi takdirde, TCHAR **char**olarak tanımlanır, normal 8-bit karakter kodlama. Bu nedenle, Unicode `CString` altında, a 16 bit karakterlerden oluşur. Unicode olmadan, türü **char**karakterleri oluşur.

Uygulamanızın Unicode programlamasını tamamlamak için şunları da yapmalısınız:

- Unicode taşınabilir olması için koşullu kodlu gerçek dizeleri için _T makro kullanın.

- Dizeleri geçtiğiniz zaman, işlev bağımsız değişkenlerinin karakterlerde uzunluk mu yoksa baytlarda uzunluk mu gerektirdiğine dikkat edin. Unicode dizeleri kullanıyorsanız fark önemlidir.

- C çalışma zamanı dize işleme işlevlerinin taşınabilir sürümlerini kullanın.

- Karakterler ve karakter işaretçileri için aşağıdaki veri türlerini kullanın:

  - **Char**kullanacağınız TCHAR'ı kullanın.

  - **Char**<strong>\*</strong>kullanacağınız LPTSTR'yi kullanın.

  - **Const char**<strong>\*</strong>kullanacağınız LPCTSTR'yi kullanın. `CString`lpctstr arasında `CString` dönüştürmek için operatör LPCTSTR sağlar.

`CString`Ayrıca Unicode'a duyarlı yapıcılar, atama işleçleri ve karşılaştırma işleçleri de sağlar.

[Run-Time Kitaplığı Başvurusu,](../c-runtime-library/c-run-time-library-reference.md) tüm dize işleme işlevlerinin taşınabilir sürümlerini tanımlar. Daha fazla bilgi için [Internationalization](../c-runtime-library/internationalization.md)kategorisine bakın.

## <a name="mfc-support-for-mbcs-strings"></a>MBCS Dizeleri için MFC Desteği

Sınıf kitaplığı, çok bayt karakter kümeleri için, ancak yalnızca çift bayt karakter kümeleri (DBCS) için de etkinleştirilir.

Çok bayt karakter kümesinde, bir karakter bir veya iki bayt genişliğinde olabilir. İki bayt genişliğindeyse, ilk baytı, hangi kod sayfasının kullanıldığına bağlı olarak belirli bir aralıktan seçilen özel bir "kurşun bayt"tır. Birlikte ele alındığında, kurşun ve "iz bayt" benzersiz bir karakter kodlama belirtin.

_MBCS sembolü, programınızın bir yapısı için tanımlanmışsa, `CString` üzerinde temel alan TCHAR yazısını, **haritaları char'a**göre yazın. Hangi baytların `CString` kurşun bayt, hangilerinin iz bayt olduğunu belirlemek size kalmış. C çalışma zamanı kitaplığı, bunu belirlemenize yardımcı olacak işlevleri sağlar.

DBCS altında, belirli bir dize tüm tek bayt ANSI karakterleri, tüm çift bayt karakterleri veya ikisinin bir birleşimini içerebilir. Bu olasılıklar, dizeleri ayrışdırma özel bakım gerektirir. Bu `CString` nesneleri içerir.

> [!NOTE]
> MFC'deki Unicode dize serileştirme, çalıştırdığınız uygulamanın hangi sürümünden bağımsız olarak hem Unicode hem de MBCS dizelerini okuyabilir. Veri dosyalarınız, programınızın Unicode ve MBCS sürümleri arasında taşınabilir.

`CString`üye işlevler, çağırdıkları C çalışma zamanı işlevlerinin özel "genel metin" sürümlerini veya Unicode'a duyarlı işlevleri kullanırlar. Bu nedenle, örneğin, `CString` bir işlev `strcmp`genellikle çağırırsa, bunun `_tcscmp` yerine karşılık gelen genel metin işlevini çağırır. _MBCS ve _UNICODE sembollerin innasıl `_tcscmp` tanımlandığına bağlı olarak, aşağıdaki gibi haritalar:

|||
|-|-|
|_MBCS tanımlanmış|`_mbscmp`|
|_UNICODE tanımlanmış|`wcscmp`|
|Ne sembol tanımlı|`strcmp`|

> [!NOTE]
> _MBCS ve _UNICODE sembolleri birbirini dışlar.

Tüm çalışma zamanı dize işleme yordamları için genel metin işlev eşlemeleri [C Run-Time Kitaplık Başvurusu'nda](../c-runtime-library/c-run-time-library-reference.md)tartışılır. Bir liste için [Internationalization'a](../c-runtime-library/internationalization.md)bakın.

Benzer şekilde, `CString` yöntemler genel veri türü eşlemeleri kullanılarak uygulanır. Hem MBCS hem de Unicode'u etkinleştirmek `wchar_t`için, MFC **Char** veya , **LPTSTR** <strong>\*</strong> char `const wchar_t*`veya **const char** <strong>\*</strong> veya `wchar_t*`. Bunlar, MBCS veya Unicode için doğru eşlemeleri sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Dizeleri (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Dize Düzenlemesi](../c-runtime-library/string-manipulation-crt.md)
