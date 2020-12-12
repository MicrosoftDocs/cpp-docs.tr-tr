---
description: 'Daha fazla bilgi edinin: Unicode ve çok baytlı karakter kümesi (MBCS) desteği'
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
ms.openlocfilehash: 9e9a09777e835872a5c8bc6613460478acf9be9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166414"
---
# <a name="unicode-and-multibyte-character-set-mbcs-support"></a>Unicode ve çok baytlı karakter kümesi (MBCS) desteği

Örneğin, Japonca ve Çince gibi bazı dillerin büyük karakter kümeleri vardır. Bu pazarlar için programlamayı desteklemek amacıyla, Microsoft Foundation Class Kitaplığı (MFC) büyük karakter kümelerini işlemek için iki farklı yaklaşım sağlar:

- [Unicode](#mfc-support-for-unicode-strings), **`wchar_t`** tabanlı GENIŞ karakterler ve UTF-16 olarak kodlanmış dizeler.

- [Çok baytlı karakter kümeleri (MBCS)](#mfc-support-for-mbcs-strings), **`char`** bir yerel ayara özgü karakter kümesinde kodlanmış tek veya çift baytlık karakterler ve dizeler.

Microsoft tüm yeni geliştirmelerde MFC Unicode kitaplıklarını önermiştir ve Visual Studio 2013 ve Visual Studio 2015 ' de MBCS kitaplıkları kullanım dışıdır. Bu durum artık geçerli değildir. Visual Studio 2017 ' de MBCS kullanımdan kaldırma uyarıları kaldırılmıştır.

## <a name="mfc-support-for-unicode-strings"></a>Unicode dizeleri için MFC desteği

Tüm MFC sınıf kitaplığı, UTF-16 olarak geniş karakterlerle depolanan Unicode karakterler ve dizeler için koşullu olarak etkinleştirilmiştir. Özellikle, Class [CString](../atl-mfc-shared/reference/cstringt-class.md) Unicode etkindir.

Bu kitaplık, hata ayıklayıcı ve DLL dosyaları MFC 'de Unicode 'U desteklemek için kullanılır:

:::row:::
   :::column span="":::
      MFC *Sürüm* U. LIB \
      MFC *Sürüm* ud 'si. LIB
      MFCM *Sürüm* U. LIB \
      MFCM *Sürüm* ud. LIB
      MFCS *Sürüm* U. LIB \
      MFCS *Sürüm* ud. LIB
      UıAFXFA. LIB
      UıAFXCWD. LıB
   :::column-end:::
   :::column span="":::
      MFC *Sürüm* U. pdb \
      MFC *Sürüm* ud 'si. PDB
      MFCM *Sürüm* U. pdb \
      MFCM *Sürüm* ud. PDB
      MFCS *Sürüm* U. pdb \
      MFCS *Sürüm* ud. PDB
      UıAFXFA. PDB
      UıAFXCWD. PDB
   :::column-end:::
   :::column span="":::
      MFC *sürüm* U.DLL \
      MFC *sürüm* UD.DLL \
      MFCM *sürüm* U.DLL \
      MFCM *sürüm* UD.DLL
   :::column-end:::
:::row-end:::

(*Sürüm* , dosyanın sürüm numarasını temsil eder; örneğin, ' 140 ', sürüm 14,0 anlamına gelir.)

`CString` , TCHAR veri türünü temel alır. Sembol _UNICODE programınızın bir derlemesi için tanımlandıysa, TCHAR türü **`wchar_t`** , 16 bitlik bir karakter kodlama türü olarak tanımlanır. Aksi halde, TCHAR, **`char`** normal 8 bit karakter kodlaması olarak tanımlanır. Bu nedenle, Unicode altında a `CString` 16 bit karakterden oluşur. Unicode olmadan, türündeki karakterlerden oluşur **`char`** .

Uygulamanızın Unicode programlamayı tamamlamaya yönelik olarak, şunları da yapmanız gerekir:

- Unicode 'a taşınabilir olması için _T makrosunu kullanarak değişmez dizeleri koşullu olarak kodlayın.

- Dizeleri geçirdiğinizde, işlev bağımsız değişkenlerinin karakter uzunluğunda veya bayt cinsinden bir uzunluğa ihtiyacı olup olmadığına dikkat edin. Unicode dizeleri kullanıyorsanız, fark önemlidir.

- C çalışma zamanı dize işleme işlevlerinin taşınabilir sürümlerini kullanın.

- Karakterler ve karakter işaretçileri için aşağıdaki veri türlerini kullanın:

  - Kullanacağınız TCHAR 'ı kullanın **`char`** .

  - Kullanacağınız LPTSTR kullanın **`char`** <strong>\*</strong> .

  - Kullandığınız LPCTSTR ' i kullanın **`const char`** <strong>\*</strong> . `CString` ve LPCTSTR arasında dönüştürme yapmak için LPCTSTR işlecini sağlar `CString` .

`CString` Ayrıca Unicode kullanan oluşturucular, atama işleçleri ve karşılaştırma işleçleri sağlar.

[Çalışma zamanı kitaplık başvurusu](../c-runtime-library/c-run-time-library-reference.md) , tüm dize işleme işlevlerinin taşınabilir sürümlerini tanımlar. Daha fazla bilgi için bkz. Kategori [Uluslararası duruma getirme](../c-runtime-library/internationalization.md).

## <a name="mfc-support-for-mbcs-strings"></a>MBCS dizeleri için MFC desteği

Sınıf kitaplığı aynı zamanda çok baytlı karakter kümeleri için de etkinleştirilir, ancak yalnızca çift baytlı karakter kümeleri için (DBCS).

Çok baytlı bir karakter kümesinde bir karakter bir veya iki bayt genişliğinde olabilir. İki baytlık bir genişse, ilk baytı, hangi kod sayfasının kullanımda olduğuna bağlı olarak belirli bir aralıktan seçilen özel bir "ön bayt" olur. Birlikte alınan, lider ve "iz baytları" benzersiz bir karakter kodlaması belirtir.

Sembol _MBCS programınızın bir derlemesi için tanımlıysa, üzerine, üzerine `CString` ile eşlenir **`char`** . Bir içinde hangi baytların `CString` ön bayt olduğunu ve bu baytların iz bayt olduğunu belirlemektir. C çalışma zamanı kitaplığı, bunu belirlemenize yardımcı olmak için işlevler sağlar.

DBCS altında, belirli bir dize tüm tek baytlı ANSI karakterlerini, tüm çift baytlı karakterleri veya ikisinin birleşimini içerebilir. Bu olasılıklar, dizeleri ayrıştırırken özel bir ilgilenmesini gerektirir. Bu `CString` nesneleri içerir.

> [!NOTE]
> MFC 'de Unicode dize serileştirme, çalıştırdığınız uygulamanın hangi sürümünden bağımsız olarak hem Unicode hem de MBCS dizelerini okuyabilir. Veri dosyalarınız, programınızın Unicode ve MBCS sürümleri arasında taşınabilir.

`CString` üye işlevleri, çağırdıkları C çalışma zamanı işlevlerinin özel "genel metin" sürümlerini kullanır veya Unicode kullanan işlevleri kullanır. Bu nedenle, örneğin, bir `CString` işlev genellikle çağrıyorsa, `strcmp` bunun yerine karşılık gelen genel metin işlevini çağırır `_tcscmp` . Simgelerin _MBCS ve _UNICODE nasıl tanımlandığına bağlı olarak, `_tcscmp` aşağıdaki gibi haritalar:

|Simgeleri|İşlev|
|-|-|
|_MBCS tanımlanmış|`_mbscmp`|
|_UNICODE tanımlanmış|`wcscmp`|
|Sembol tanımlı değil|`strcmp`|

> [!NOTE]
> _MBCS ve _UNICODE sembolleri birbirini dışlıyor.

Tüm çalışma zamanı dize işleme yordamlarının genel metin işlev eşlemeleri, [C Run-Time kitaplığı başvurusunda](../c-runtime-library/c-run-time-library-reference.md)ele alınmıştır. Bir liste için bkz. [Uluslararası duruma getirme](../c-runtime-library/internationalization.md).

Benzer şekilde, `CString` Yöntemler genel veri türü eşlemeleri kullanılarak uygulanır. Hem MBCS hem de UNICODE 'u etkinleştirmek için MFC, veya için **`char`** , veya için bir **`wchar_t`** **`char`** <strong>\*</strong> `wchar_t*`  <strong>\*</strong> `const wchar_t*` Bu, MBCS veya Unicode için doğru eşlemeleri güvence altına aldığından emin olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Dize Düzenlemesi](../c-runtime-library/string-manipulation-crt.md)
