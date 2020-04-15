---
title: Dize Veri Yönetimi
ms.date: 11/04/2016
helpviewer_keywords:
- Unicode, string objects
ms.assetid: 0b53a542-eeb1-4108-9ada-6700645b6f8f
ms.openlocfilehash: 7f92b38ac659faef2dd9319b2f204ba837f0d473
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317460"
---
# <a name="string-data-management"></a>Dize Veri Yönetimi

Visual C++ dize verilerini yönetmenin çeşitli yollarını sağlar:

- C stili null-sonlandırılan dizeleri ile çalışmak için [String Manipülasyon](../c-runtime-library/string-manipulation-crt.md)

- Dizeleri yönetmek için Win32 API işlevleri

- MFC'nin esnek, yeniden boyutlandırılabilir dize nesneleri sağlayan [CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md)

- Sınıf [CStringT Sınıfı](../atl-mfc-shared/reference/cstringt-class.md), aynı işlevsellik ile MFC bağımsız bir dize nesnesi sağlayan`CString`

Neredeyse tüm programlar dize verileriyle çalışır. MFC'nin `CString` sınıfı genellikle esnek dize işleme için en iyi çözümdür. Sürüm 7.0 ile `CString` başlayarak, MFC veya MFC bağımsız programlarda kullanılabilir. Hem çalışma zamanı kitaplığı hem de Unicode veya `CString` MBCS programlamada olduğu gibi çok bayt (geniş) karakterler içeren destek dizeleri.

Bu makalede, sınıf kitaplığı dize işleme ile ilgili sağladığı genel amaçlı hizmetleri açıklanır. Bu makalede ele alınan konular şunlardır:

- [Unicode ve MBCS Taşınabilirlik sağlayın](#_core_unicode_and_mbcs_provide_portability)

- [CStrings ve const char Pointers](#_core_cstrings_and_const_char_pointers)

- [CString Başvuru Sayımı](#_core_cstring_reference_counting)

[CStringT Sınıfı](../atl-mfc-shared/reference/cstringt-class.md) sınıfı dizeleri işlemek için destek sağlar. Normalde C çalışma zamanı kitaplık dize paketi tarafından sağlanan işlevselliği değiştirmek ve genişletmek için tasarlanmıştır. Sınıf, `CString` Temel'de bulunanlara benzer şekilde basitleştirilmiş dize işleme için üye işlevleri ve işleçleri sağlar. Sınıf `CString`ayrıca, s ve standart C++ dize veri türlerinin oluşturulması, atanması ve karşılaştırılması için oluşturucular ve işleçler de sağlar. Türetilen `CString` `CObject`olmadığından, microsoft hazırlık `CString` sınıf kitaplığı (MFC) çoğubağımsız nesneleri kullanabilirsiniz.

`CString`nesneler "değer semantik" izleyin. Nesne `CString` benzersiz bir değeri temsil eder. Bir dize `CString` için bir işaretçi olarak değil, gerçek bir dize olarak düşünün.

Bir `CString` nesne değişken karakter sayısının sırasını temsil eder. `CString`nesneler karakter dizileri olarak düşünülebilir.

## <a name="unicode-and-mbcs-provide-portability"></a><a name="_core_unicode_and_mbcs_provide_portability"></a>Unicode ve MBCS Taşınabilirlik sağlar

MFC sürüm 3.0 ve sonraki sürümlerde, Hem Unicode hem de multibayt karakter kümeleri (MBCS) için MFC `CString`etkindir. Bu destek, Unicode veya ANSI karakterleri için oluşturabileceğiniz taşınabilir uygulamaları yazmanızı kolaylaştırır. Bu taşınabilirliği etkinleştirmek için, `CString` bir nesnedeki her karakter, `wchar_t` uygulamanızı oluştururken _UNICODE veya değilmiş gibi `char` simgeyi tanımlıyormuş gibi tanımlanan TCHAR türündendir. Bir `wchar_t` karakter 16 bit genişliğindedir. Tanımlanan _MBCS sembolüyle oluşturursanız MBCS etkinleştirilir. MFC kendisi ya _MBCS sembolü (NAFX kitaplıkları için) veya _UNICODE sembolü (UAFX kitaplıklar için) tanımlanmış ile inşa edilmiştir.

> [!NOTE]
> Bu `CString` ve dizeleri üzerinde eşlik eden makalelerde örnekler düzgün Unicode taşınabilirlik için biçimlendirilmiş edebi dizeleri göstermek, _T makro kullanarak, hangi forma edebi dize çevirir:

`L"literal string"`

> [!NOTE]
> derleyicinin Unicode dizesi olarak ele aldığı. Örneğin, aşağıdaki kod:

[!code-cpp[NVC_ATLMFC_Utilities#187](../atl-mfc-shared/codesnippet/cpp/string-data-management_1.cpp)]

> [!NOTE]
> _UNICODE tanımlıysa Unicode dizesi olarak veya tanımlanmamışsa ANSI dizesi olarak çevrilir. Daha fazla bilgi için [Unicode ve Multibyte Karakter Kümesi (MBCS) Desteği makalesine](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)bakın.

Bir `CString` nesne en fazla INT_MAX (2.147.483.647) karakter depolayabilir. TCHAR veri türü, bir `CString` nesnenin içindeki karakterleri almak veya ayarlamak için kullanılır. Karakter dizilerinin aksine, `CString` sınıfın yerleşik bellek ayırma özelliği vardır. Bu, `CString` nesnelerin gerektiği gibi otomatik olarak büyümesine izin verir (diğer `CString` bir zamanda, daha uzun dizeleri sığdıracak bir nesne yetiştirme konusunda endişelenmenize gerek yoktur).

## <a name="cstrings-and-const-char-pointers"></a><a name="_core_cstrings_and_const_char_pointers"></a>CStrings ve const char Pointers

Bir `CString` nesne aynı zamanda gerçek bir C stili `PCXSTR`dize gibi hareket edebilir (bir , Unicode altında değilse **const char** <strong>\*</strong> aynıdır). [CSimpleStringT::işleç PCXSTR](../atl-mfc-shared/reference/csimplestringt-class.md#operator_pcxstr) dönüştürme `CString` işleci, nesnelerin işlev çağrılarında karakter işaretçileri için serbestçe değiştirilmesine izin verir. **CString (LPCWSTR)** `pszSrc` **)** oluşturucu karakter işaretçileri nesneleri `CString` yerine izin verir.

Nesneleri katlamak `CString` için hiçbir girişimde bulunulmadı. Örneğin, iki `CString` nesne `Chicago`içeren yaparsanız, karakterler `Chicago` iki yerde depolanır. (Bu, MFC'nin gelecekteki sürümleri için geçerli olmayabilir, bu nedenle buna bağlı olmamalısınız.)

> [!NOTE]
> [CSimpleStringT kullanın::GetBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) ve [CSimpleStringT::ReleaseBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) üye işlevleri doğrudan `CString` bir karakter için sabit olmayan bir işaretçi olarak erişmek gerekir.

> [!NOTE]
> Otomasyonda kullanılan BSTR nesnelerini (eski adıyla OLE Automation olarak bilinir) ayırmak ve ayarlamak için [CStringT:AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring) ve [CStringT::SetSysString](../atl-mfc-shared/reference/cstringt-class.md#setsysstring) üye işlevlerini kullanın.

> [!NOTE]
> Mümkün olduğunda, `CString` nesneleri yığın yerine çerçeveye ayırın. Bu bellek kaydeder ve parametre geçişini kolaylaştırır.

Sınıf `CString` Microsoft Hazırlık Sınıfı Kitaplığı koleksiyonu sınıfı olarak `CString` uygulanmaz, ancak nesneler koleksiyonlarda öğeler olarak kesinlikle depolanabilir.

## <a name="cstring-reference-counting"></a><a name="_core_cstring_reference_counting"></a>CString Başvuru Sayımı

MFC sürüm 4.0 itibariyle, [CStringT Sınıf](../atl-mfc-shared/reference/cstringt-class.md) nesneleri kopyalandığında, MFC verileri kopyalamak yerine bir başvuru sayısı artışlar. Bu, parametreleri değere `CString` göre geçirmeve nesneleri değere göre döndürmeyi daha verimli hale getirir. Bu işlemler, kopya oluşturucunun bazen birden fazla kez çağrılmasını neden olur. Başvuru sayısını niçin artım, bu yaygın işlemler için `CString` ek yükü azaltır ve daha cazip bir seçenek kullanır.

Her kopya yok edildikçe, özgün nesnedeki başvuru sayısı verilir. Özgün `CString` nesne, başvuru sayısı sıfıra indirilene kadar yok edilmez.

`CString` [CSimpleStringT::LockAraffer](../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) ve [CSimpleStringT::UnlockBuffer'ı](../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) kullanarak başvuru sayma kullanımını devre dışı bırakın veya etkinleştirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)
