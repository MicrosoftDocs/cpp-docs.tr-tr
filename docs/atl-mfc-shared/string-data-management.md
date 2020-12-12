---
description: 'Hakkında daha fazla bilgi edinin: dize Veri Yönetimi'
title: Dize Veri Yönetimi
ms.date: 11/04/2016
helpviewer_keywords:
- Unicode, string objects
ms.assetid: 0b53a542-eeb1-4108-9ada-6700645b6f8f
ms.openlocfilehash: 37a3a13dc58641cc23e8ea5c31e12a4d4d9582fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166518"
---
# <a name="string-data-management"></a>Dize Veri Yönetimi

Visual C++ dize verilerini yönetmek için çeşitli yollar sağlar:

- C stili null ile sonlandırılmış dizeler ile çalışmaya yönelik [dize düzenlemesi](../c-runtime-library/string-manipulation-crt.md)

- Dizeleri yönetmek için Win32 API işlevleri

- MFC 'nin sınıf [CStringT](../atl-mfc-shared/reference/cstringt-class.md)sınıfı, esnek, yeniden boyutlandırılabilir dize nesneleri sağlar

- Sınıfında aynı işlevselliğe sahip MFC bağımsız dize nesnesi sağlayan [CStringT](../atl-mfc-shared/reference/cstringt-class.md)sınıfı sınıfı `CString`

Neredeyse tüm programlar dize verileriyle çalışır. MFC 'nin `CString` sınıfı genellikle esnek dize işleme için en iyi çözümdür. Sürüm 7,0 ' den başlayarak `CString` MFC veya mfc bağımsız programlarda kullanılabilir. Hem çalışma zamanı kitaplığı hem de `CString` çok baytlı (geniş) karakter içeren dizeleri Unicode veya MBCS programlamasında destekler.

Bu makalede, sınıf kitaplığının dize düzenlemesi ile ilgili sağladığı genel amaçlı hizmetler açıklanır. Bu makalede ele alınan konular şunları içerir:

- [Unicode ve MBCS taşınabilirlik sağlar](#_core_unicode_and_mbcs_provide_portability)

- [CStrings ve const char Işaretçileri](#_core_cstrings_and_const_char_pointers)

- [CString başvuru sayımı](#_core_cstring_reference_counting)

[CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md) sınıfı, dizeleri işlemek için destek sağlar. Normalde C çalışma zamanı kitaplığı dize paketi tarafından sunulan işlevselliği değiştirmek ve genişletmek için tasarlanmıştır. `CString`Sınıfı, temel içinde bulunanlara benzer şekilde Basitleştirilmiş dize işleme için üye işlevleri ve işleçler sağlar. Sınıfı ayrıca, `CString` s ve standart C++ dize veri türlerini oluşturmak, atamak ve karşılaştırmak için oluşturucular ve işleçler sağlar. , `CString` Öğesinden türetilmediği `CObject` `CString` için NESNELERI Microsoft Foundation Class Kitaplığı (MFC) büyük bir kısmından bağımsız olarak kullanabilirsiniz.

`CString` nesneler "değer semantiğini" izler. Bir `CString` nesne benzersiz bir değeri temsil eder. Bir `CString` dizenin işaretçisi olarak değil, gerçek bir dize olarak düşünün.

Bir `CString` nesne, değişken sayıda karakter dizisini temsil eder. `CString` nesneler, karakter dizileri olarak düşünülebilir.

## <a name="unicode-and-mbcs-provide-portability"></a><a name="_core_unicode_and_mbcs_provide_portability"></a> Unicode ve MBCS taşınabilirlik sağlar

MFC sürüm 3,0 ve sonrasında MFC, dahil `CString` , hem Unicode hem çok baytlı karakter kümesi (MBCS) için etkinleştirilir. Bu destek, Unicode veya ANSI karakterleri için oluşturabileceğiniz taşınabilir uygulamalar yazmanızı kolaylaştırır. Bu taşınabilirliği etkinleştirmek için, bir nesnedeki her bir karakter, `CString` **`wchar_t`** uygulamanızı oluştururken _UNICODE, simge tanımladığınıza göre tanımlanan TCHAR türündedir **`char`** . Bir **`wchar_t`** karakter 16 bit geniştir. _MBCS tanımlanmış sembol ile derleme yapıyorsanız MBCS etkinleştirilir. MFC kendisi _MBCS simgesiyle (NAFX kitaplıkları için) veya tanımlanan _UNICODE sembolüyle (UAFX kitaplıkları için) oluşturulur.

> [!NOTE]
> `CString`Bu ve dizelerde bulunan makalelerdeki örnekler, değişmez dizeyi şu biçimde çeviren _T makrosunu kullanarak Unicode taşınabilirliği için düzgün şekilde biçimlendirilen sabit dizeler gösterir:

`L"literal string"`

> [!NOTE]
> derleyicinin bir Unicode dize olarak davrandığı. Örneğin, aşağıdaki kod:

[!code-cpp[NVC_ATLMFC_Utilities#187](../atl-mfc-shared/codesnippet/cpp/string-data-management_1.cpp)]

> [!NOTE]
> _UNICODE tanımlanmışsa bir Unicode dizesi olarak veya değilse bir ANSI dizesi olarak çevrilir. Daha fazla bilgi için bkz. [Unicode ve çok baytlı karakter kümesi (MBCS) desteği](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).

Bir `CString` nesne, en fazla INT_MAX (2.147.483.647) karakter saklayabilir. Bir nesne içindeki karakterleri almak veya ayarlamak için TCHAR veri türü kullanılır `CString` . Karakter dizilerinin aksine, `CString` sınıfının yerleşik bir bellek ayırma özelliği vardır. Bu `CString` , nesnelerin gerektikçe otomatik olarak büyümesini sağlar (yani, bir `CString` nesneyi daha uzun dizelere sığacak şekilde büyüyen endişelenmeniz gerekmez).

## <a name="cstrings-and-const-char-pointers"></a><a name="_core_cstrings_and_const_char_pointers"></a> CStrings ve const char Işaretçileri

Bir `CString` nesne aynı zamanda bir C stili dize ( `PCXSTR` Unicode altında değilse **const char** ile aynı) gibi davranabilir <strong>\*</strong> . [CSimpleStringT:: operator PCXSTR](../atl-mfc-shared/reference/csimplestringt-class.md#operator_pcxstr) dönüştürme işleci, `CString` nesnelerin işlev çağrılarında karakter işaretçileri için serbestçe kullanılmasına izin verir. **CString (LPCWSTR** `pszSrc` **)** Oluşturucusu, karakter işaretçilerinin nesneler için yerine geçmesini sağlar `CString` .

Nesneleri katlamak için girişimde bulunuldu `CString` . Örneğin, içeren iki `CString` nesne yaparsanız, `Chicago` içindeki karakterler `Chicago` iki yerde saklanır. (Bu, daha sonraki MFC sürümlerinin doğru olmayabilir, bu yüzden buna bağlı kullanmamalısınız.)

> [!NOTE]
> Bir karaktere sabit olmayan bir işaretçi olarak doğrudan erişmeniz gerektiğinde [CSimpleStringT:: GetBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) ve [CSimpleStringT:: ReleaseBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) üye işlevlerini kullanın `CString` .

> [!NOTE]
> Otomasyon 'da kullanılan BSTR nesnelerini ayırmak ve ayarlamak için [CStringT:: AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring) ve [CStringT:: setsysstring](../atl-mfc-shared/reference/cstringt-class.md#setsysstring) üye işlevlerini kullanın (eski adı OLE Automation olarak bilinir).

> [!NOTE]
> Mümkün olduğunda, `CString` nesneleri yığında değil çerçevede ayırır. Bu, belleği kaydeder ve parametre geçişini basitleştirir.

`CString`Sınıf bir Microsoft Foundation Class Kitaplığı Collection sınıfı olarak uygulanmıyor, ancak `CString` nesneler koleksiyonlarda tamamen öğe olarak depolanabilir.

## <a name="cstring-reference-counting"></a><a name="_core_cstring_reference_counting"></a> CString başvuru sayımı

MFC sürüm 4,0 itibariyle, [CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md) nesneleri KOPYALANDıĞıNDA, MFC verileri kopyalamak yerine bir başvuru sayısını artırır. Bu, parametreleri değere göre geçirmeyi ve `CString` nesneleri değere göre döndürmeyi daha verimli hale getirir. Bu işlemler kopyalama oluşturucusunun bazen birden çok kez çağrılmasına neden olur. Bir başvuru sayısını artırma, bu ortak işlemler için bu ek yükü azaltır ve `CString` daha etkileyici bir seçenek kullanmayı sağlar.

Her kopya yok edildiğinde, özgün nesnedeki başvuru sayısı azaltılır. Özgün `CString` nesne, başvuru sayısı sıfıra Düşürülünceye kadar yok edilmez.

`CString`Başvuru saymayı devre dışı bırakmak veya etkinleştirmek Için [CSimpleStringT:: LockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) ve [CSimpleStringT:: UnlockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) üye işlevlerini kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Genel MFC konuları](../mfc/general-mfc-topics.md)
