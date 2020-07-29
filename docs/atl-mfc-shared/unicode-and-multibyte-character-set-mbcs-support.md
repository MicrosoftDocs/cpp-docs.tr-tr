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
ms.openlocfilehash: 217690e09ed595bb9fa9572693bf774259c42412
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219033"
---
# <a name="unicode-and-multibyte-character-set-mbcs-support"></a>Unicode ve çok baytlı karakter kümesi (MBCS) desteği

Örneğin, Japonca ve Çince gibi bazı dillerin büyük karakter kümeleri vardır. Bu pazarlar için programlamayı desteklemek amacıyla, Microsoft Foundation Class Kitaplığı (MFC) büyük karakter kümelerini işlemek için iki farklı yaklaşım sağlar:

- [Unicode](#mfc-support-for-unicode-strings), **`wchar_t`** tabanlı GENIŞ karakterler ve UTF-16 olarak kodlanmış dizeler.

- [Çok baytlı karakter kümeleri (MBCS)](#mfc-support-for-mbcs-strings), **`char`** bir yerel ayara özgü karakter kümesinde kodlanmış tek veya çift baytlık karakterler ve dizeler.

Microsoft tüm yeni geliştirmelerde MFC Unicode kitaplıklarını önermiştir ve Visual Studio 2013 ve Visual Studio 2015 ' de MBCS kitaplıkları kullanım dışıdır. Bu durum artık geçerli değildir. Visual Studio 2017 ' de MBCS kullanımdan kaldırma uyarıları kaldırılmıştır.

## <a name="mfc-support-for-unicode-strings"></a>Unicode dizeleri için MFC desteği

Tüm MFC sınıf kitaplığı, UTF-16 olarak geniş karakterlerle depolanan Unicode karakterler ve dizeler için koşullu olarak etkinleştirilmiştir. Özellikle, Class [CString](../atl-mfc-shared/reference/cstringt-class.md) Unicode etkindir.

Bu kitaplık, hata ayıklayıcı ve DLL dosyaları MFC 'de Unicode 'U desteklemek için kullanılır:

|||||
|-|-|-|-|
|UıAFXFA. LıB|UıAFXFA. PDB|UıAFXCWD. LıB|UıAFXCWD. PDB|
|MFC*Sürüm*U. LIB|MFC*Sürüm*U. pdb|MFC*sürüm*U.DLL|MFC*Sürüm*ud 'si. LıB|
|MFC*Sürüm*ud 'si. PDB|MFC*sürüm*UD.DLL|MFCS*Sürüm*U. LIB|MFCS*Sürüm*U. pdb|
|MFCS*Sürüm*ud. LıB|MFCS*Sürüm*ud. PDB|MFCM*Sürüm*U. LIB|MFCM*Sürüm*U. pdb|
|MFCM*sürüm*U.DLL|MFCM*Sürüm*ud. LıB|MFCM*Sürüm*ud. PDB|MFCM*sürüm*UD.DLL|

(*Sürüm* , dosyanın sürüm numarasını temsil eder; örneğin, ' 140 ', sürüm 14,0 anlamına gelir.)

`CString`, TCHAR veri türünü temel alır. Sembol _UNICODE programınızın bir derlemesi için tanımlandıysa, TCHAR türü **`wchar_t`** , 16 bitlik bir karakter kodlama türü olarak tanımlanır. Aksi halde, TCHAR, **`char`** normal 8 bit karakter kodlaması olarak tanımlanır. Bu nedenle, Unicode altında a `CString` 16 bit karakterden oluşur. Unicode olmadan, türündeki karakterlerden oluşur **`char`** .

Uygulamanızın Unicode programlamayı tamamlamaya yönelik olarak, şunları da yapmanız gerekir:

- Unicode 'a taşınabilir olması için _T makrosunu kullanarak değişmez dizeleri koşullu olarak kodlayın.

- Dizeleri geçirdiğinizde, işlev bağımsız değişkenlerinin karakter uzunluğunda veya bayt cinsinden bir uzunluğa ihtiyacı olup olmadığına dikkat edin. Unicode dizeleri kullanıyorsanız, fark önemlidir.

- C çalışma zamanı dize işleme işlevlerinin taşınabilir sürümlerini kullanın.

- Karakterler ve karakter işaretçileri için aşağıdaki veri türlerini kullanın:

  - Kullanacağınız TCHAR 'ı kullanın **`char`** .

  - Kullanacağınız LPTSTR kullanın **`char`** <strong>\*</strong> .

  - **Const char**'ı kullanacağınız LPCTSTR kullanın <strong>\*</strong> . `CString`ve LPCTSTR arasında dönüştürme yapmak için LPCTSTR işlecini sağlar `CString` .

`CString`Ayrıca Unicode kullanan oluşturucular, atama işleçleri ve karşılaştırma işleçleri sağlar.

[Çalışma zamanı kitaplık başvurusu](../c-runtime-library/c-run-time-library-reference.md) , tüm dize işleme işlevlerinin taşınabilir sürümlerini tanımlar. Daha fazla bilgi için bkz. Kategori [Uluslararası duruma getirme](../c-runtime-library/internationalization.md).

## <a name="mfc-support-for-mbcs-strings"></a>MBCS dizeleri için MFC desteği

Sınıf kitaplığı aynı zamanda çok baytlı karakter kümeleri için de etkinleştirilir, ancak yalnızca çift baytlı karakter kümeleri için (DBCS).

Çok baytlı bir karakter kümesinde bir karakter bir veya iki bayt genişliğinde olabilir. İki baytlık bir genişse, ilk baytı, hangi kod sayfasının kullanımda olduğuna bağlı olarak belirli bir aralıktan seçilen özel bir "ön bayt" olur. Birlikte alınan, lider ve "iz baytları" benzersiz bir karakter kodlaması belirtir.

Sembol _MBCS programınızın bir derlemesi için tanımlıysa, üzerine, üzerine `CString` ile eşlenir **`char`** . Bir içinde hangi baytların `CString` ön bayt olduğunu ve bu baytların iz bayt olduğunu belirlemektir. C çalışma zamanı kitaplığı, bunu belirlemenize yardımcı olmak için işlevler sağlar.

DBCS altında, belirli bir dize tüm tek baytlı ANSI karakterlerini, tüm çift baytlı karakterleri veya ikisinin birleşimini içerebilir. Bu olasılıklar, dizeleri ayrıştırırken özel bir ilgilenmesini gerektirir. Bu `CString` nesneleri içerir.

> [!NOTE]
> MFC 'de Unicode dize serileştirme, çalıştırdığınız uygulamanın hangi sürümünden bağımsız olarak hem Unicode hem de MBCS dizelerini okuyabilir. Veri dosyalarınız, programınızın Unicode ve MBCS sürümleri arasında taşınabilir.

`CString`üye işlevleri, çağırdıkları C çalışma zamanı işlevlerinin özel "genel metin" sürümlerini kullanır veya Unicode kullanan işlevleri kullanır. Bu nedenle, örneğin, bir `CString` işlev genellikle çağrıyorsa, `strcmp` bunun yerine karşılık gelen genel metin işlevini çağırır `_tcscmp` . Simgelerin _MBCS ve _UNICODE nasıl tanımlandığına bağlı olarak, `_tcscmp` aşağıdaki gibi haritalar:

|||
|-|-|
|_MBCS tanımlanmış|`_mbscmp`|
|_UNICODE tanımlanmış|`wcscmp`|
|Sembol tanımlı değil|`strcmp`|

> [!NOTE]
> _MBCS ve _UNICODE sembolleri birbirini dışlıyor.

Tüm çalışma zamanı dize işleme yordamlarının genel metin işlev eşlemeleri [C çalışma zamanı kitaplığı başvurusunda](../c-runtime-library/c-run-time-library-reference.md)ele alınmıştır. Bir liste için bkz. [Uluslararası duruma getirme](../c-runtime-library/internationalization.md).

Benzer şekilde, `CString` Yöntemler genel veri türü eşlemeleri kullanılarak uygulanır. Hem MBCS hem de UNICODE 'u etkinleştirmek için MFC, veya için **`char`** , veya için bir **`wchar_t`** **`char`** <strong>\*</strong> `wchar_t*` **const char** <strong>\*</strong> `const wchar_t*` Bu, MBCS veya Unicode için doğru eşlemeleri güvence altına aldığından emin olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Dize Düzenlemesi](../c-runtime-library/string-manipulation-crt.md)
