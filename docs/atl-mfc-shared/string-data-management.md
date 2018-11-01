---
title: Dize veri yönetimi
ms.date: 11/04/2016
helpviewer_keywords:
- Unicode, string objects
ms.assetid: 0b53a542-eeb1-4108-9ada-6700645b6f8f
ms.openlocfilehash: cbc48008cd7b30f1630fc4ec2c30214e3c448c27
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595071"
---
# <a name="string-data-management"></a>Dize veri yönetimi

Visual C++ dize verileri yönetmek için birçok yol sağlar:

- [Dize düzenlemesi](../c-runtime-library/string-manipulation-crt.md) null ile sonlandırılmış C stili dizeler ile çalışma

- Dizeleri yönetmek için Win32 API işlevleri

- MFC'nin sınıfı [CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md), esnek, yeniden boyutlandırılabilir dize nesnelerinin sağlar

- Sınıf [CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md), aynı işlevlere sahip bir MFC bağımsız dize nesnesi sağlar `CString`

Neredeyse tüm programlar dize verileri ile çalışma. MFC'nin `CString` sınıfı, genellikle esnek dize işleme için en iyi çözümü. Sürüm 7.0 `CString` MFC veya MFC bağımsız programlarında kullanılabilir. Çalışma zamanı kitaplığı ve `CString` destek Unicode veya MBCS programlama olduğu gibi (geniş) birden çok baytlı karakterler içeren bir dize.

Dize düzenlemesi için ilgili sınıf kitaplığının sağladığı genel amaçlı hizmetler bu makalede açıklanır. Bu makalede ele alınan konular:

- [Unicode ve MBCS sağlamak taşınabilirlik](#_core_unicode_and_mbcs_provide_portability)

- [CStrings ve const char işaretçiler](#_core_cstrings_and_const_char_pointers)

- [CString başvuru sayımı](#_core_cstring_reference_counting)

[CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md) sınıfı, dizeleri işlemek için destek sağlar. Değiştirin ve normalde C çalışma zamanı kitaplığı dize paketi tarafından sağlanan işlevselliği genişletmek için tasarlanmıştır. `CString` Sınıf üye işlevleri ve Basitleştirilmiş dize işleme, Basic bulunanlar benzer işleçleri sağlar. Sınıf ayrıca taşıma oluşturucuları ve işleçleri oluşturma, atama ve karşılaştırma sağlar `CString`s ve standart C++ dize veri türleri. Çünkü `CString` türünden türetilmediğinden `CObject`, kullanabileceğiniz `CString` çoğu, Microsoft Foundation Class Kitaplığı'nı (MFC) bağımsız olarak nesne.

`CString` "semantiği değeri" nesneleri izleyin A `CString` nesnesini temsil eden benzersiz bir değer. Düşünün bir `CString` gerçek bir dize olarak, bir dizeye bir işaretçi olarak değil.

A `CString` nesne bir değişken sayıda karakter dizisini temsil eder. `CString` nesneleri, karakter dizileri olarak düşünülebilir.

##  <a name="_core_unicode_and_mbcs_provide_portability"></a> Unicode ve MBCS taşınabilirlik sağlar.

MFC sürüm 3.0 ve daha sonra MFC, dahil olan `CString`, Unicode ve çok baytlı karakter kümesi (MBCS) için etkinleştirilmiş. Bu destek, Unicode veya ANSI karakterler için oluşturabileceğiniz taşınabilir uygulamaları yazmak kolaylaştırır. Bu taşınabilirlik, her bir karakteri etkinleştirmek için bir `CString` nesnedir türü olarak tanımlanmış TCHAR `wchar_t` uygulamanızı oluştururken _UNICODE tanımlarsanız veya olarak `char` Aksi takdirde. A `wchar_t` 16 bit genişliğinde karakterdir. Sembol _MBCS tanımlanmış yapı MBCS etkinleştirilir. MFC'nin (için NAFX kitaplıklar) _MBCS simgesiyle oluşturulmuştur veya _UNICODE simgesi (UAFX kitaplıklar) tanımlanmış.

> [!NOTE]
>  `CString` Örnekler bu ve eşlik eden makaleler dizeler değişmez değer dizeleri Unicode taşınabilir sabit dizesini forma çevirir _T makrosunu kullanarak, doğru şekilde biçimlendirildiğini:

`L"literal string"`

> [!NOTE]
>  Derleyici bir Unicode dize olarak değerlendirir. Örneğin, aşağıdaki kodu:

[!code-cpp[NVC_ATLMFC_Utilities#187](../atl-mfc-shared/codesnippet/cpp/string-data-management_1.cpp)]

> [!NOTE]
>  _UNICODE tanımlanmış olması durumunda bir Unicode dize veya bir ANSI dizesine değilse olarak çevrilir. Daha fazla bilgi için bkz [Unicode ve çok baytlı karakter kümesi (MBCS) desteği](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).

A `CString` nesne depolayabileceğiniz INT_MAX (2,147,483,647) karakter. TCHAR veri türünü almak veya içindeki karakterlerin tek tek ayarlamak için kullanılan bir `CString` nesne. Karakter dizilerini aksine `CString` sınıfında yerleşik bellek ayırma yeteneği. Böylece `CString` gerektiğinde otomatik olarak büyütmeyi nesneleri (diğer bir deyişle, büyüyen hakkında endişelenmeniz gerekmez bir `CString` uzun dizeler uyacak şekilde nesnesi).

##  <a name="_core_cstrings_and_const_char_pointers"></a> CStrings ve const char işaretçiler

A `CString` nesne ayrıca bir C stili, dize gibi hareket edebilir (bir `PCXSTR`, aynı olduğu **const char** <strong>\*</strong> Unicode altında ise). [CSimpleStringT::operator PCXSTR](../atl-mfc-shared/reference/csimplestringt-class.md#operator_pcxstr) dönüştürme işleci verir `CString` nesneleri serbestçe işlev çağrılarında karakter işaretçileri yerine kullanılacak. **CString (LPCWSTR** `pszSrc` **)** Oluşturucu için değiştirilecek karakter işaretçileri tanır `CString` nesneleri.

Katlama için hiç girişimde `CString` nesneleri. İki yaparsanız `CString` içeren nesneleri `Chicago`, örneğin, karakterleri `Chicago` iki yerde saklanır. (, Ona bağımlı olmaması için bu MFC, gelecek sürümlerinde doğru olmayabilir.)

> [!NOTE]
>  Kullanım [CSimpleStringT::GetBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) ve [CSimpleStringT::ReleaseBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) üye işlevleri, doğrudan erişim gerektiğinde bir `CString` bir karakter nonconstant işaretçisi olarak.

> [!NOTE]
>  Kullanım [CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring) ve [CStringT::SetSysString](../atl-mfc-shared/reference/cstringt-class.md#setsysstring) üye işlevleri ayırmak ve Otomasyon (eski adıyla OLE Otomasyonu da bilinir) kullanılan BSTR nesneleri ayarlamak için.

> [!NOTE]
>  Mümkün olduğunda, tahsis `CString` çerçevesi yerine yığındaki nesneler. Bu işlem, bellek kaydeder ve parametre geçirme basitleştirir.

`CString` Sınıfı Microsoft Foundation Class Kitaplığı koleksiyon sınıfı, ancak uygulanmadı `CString` nesneleri kesinlikle depolanabilir koleksiyonlarında bulunan öğeleri olarak.

##  <a name="_core_cstring_reference_counting"></a> CString başvuru sayımı

MFC sürüm 4.0 itibariyle, [CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md) nesneler kopyalanır, MFC, veri kopyalama yerine bir başvuru sayısını artırır. Bu değer ve parametreleri geçirme kılar `CString` daha verimli değeriyle nesneleri. Bu işlemler, bazen birden çok kez çağrılması için Kopyala oluşturucusunu neden. Bu ortak işlemler için bu ek yükünü azaltır ve yapar kullanarak bir başvuru sayısı artan `CString` daha cazip bir seçenektir.

Her kopyası yok olarak özgün nesneye başvuru sayısı azaltılır. Özgün `CString` nesne, başvuru sayısı sıfıra azaltılana kadar yok edilmez.

Kullanabileceğiniz `CString` üye işlevleri [CSimpleStringT::LockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) ve [CSimpleStringT::UnlockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) başvuru sayımı etkinleştir veya devre dışı bırakmak.

## <a name="see-also"></a>Ayrıca Bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)

