---
title: "Dize veri yönetimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords: Unicode, string objects
ms.assetid: 0b53a542-eeb1-4108-9ada-6700645b6f8f
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b0ffeebee648c6ce804879683d7236786bbcbdc9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="string-data-management"></a>Dize veri yönetimi
Visual C++ dize verilerini yönetmek için birkaç yöntem sağlar:  
  
-   [Dize düzenlemesi](../c-runtime-library/string-manipulation-crt.md) C türü null ile sonlandırılmış dizeler ile çalışma  
  
-   Dizeleri yönetmek için Win32 API işlevleri  
  
-   MFC'nin sınıfı [CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md), esnek ve yeniden boyutlandırılabilir dize nesnelerini sağlar  
  
-   Sınıf [CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md), aynı işlevselliği ile bir MFC bağımsız dize nesnesi sağlar`CString`  
  
 Neredeyse tüm programlar dize verilerle çalışır. MFC'nin `CString` sınıfı, genellikle en iyi çözüm esnek dize işleme. 7.0 sürümünden başlayarak `CString` MFC veya MFC bağımsız programlarda kullanılabilir. Her iki çalışma zamanı kitaplığı ve `CString` destek Unicode veya MBCS programlama olduğu gibi (geniş) birden çok baytlı karakterler içeren bir dize.  
  
 Bu makalede dize düzenlemesi için ilgili sınıf kitaplığı sağladığı genel amaçlı Hizmetleri açıklanmaktadır. Bu makalede ele alınan konular şunlardır:  
  
-   [Unicode ve MBCS sağlamak taşınabilirlik](#_core_unicode_and_mbcs_provide_portability)  
  
-   [CStrings ve const char işaretçiler](#_core_cstrings_and_const_char_pointers)  
  
-   [CString başvuru sayım](#_core_cstring_reference_counting)  
  
 [CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md) sınıfı, dizeleri düzenleme için destek sağlar. Değiştirin ve genellikle C çalışma zamanı kitaplığı dizesi paketi tarafından sağlanan işlevselliği genişletmek için tasarlanmıştır. `CString` Sınıf üyesi işlevleri ve Basitleştirilmiş dize işleme, Basic içinde bulunan benzer işleçleri sağlar. Sınıf oluşturucular ve de işleçleri oluşturma, atama ve karşılaştırma için sağlar **CStrings** ve standart C++ dize veri türleri. Çünkü `CString` türetilmedi `CObject`, kullanabileceğiniz `CString` çoğu Microsoft Foundation Class Kitaplığı (MFC) bağımsız olarak nesneleri.  
  
 `CString`"semantiği değeri." nesneleri izleyin A `CString` nesnesi benzersiz bir değeri temsil eder. Düşünün bir `CString` gerçek bir dize olarak, bir dize için bir işaretçi olarak değil.  
  
 A `CString` nesne bir değişken karakter sayısını dizisini temsil eder. `CString`nesneleri, karakter dizileri olarak düşünülebilir.  
  
##  <a name="_core_unicode_and_mbcs_provide_portability"></a>Unicode ve MBCS taşınabilirlik sağlayın  
 Sürüm 3.0 ve üstü, MFC, MFC dahil olmak üzere ile `CString`, Unicode ve çok baytlı karakter kümeleri (MBCS) için etkinleştirilmiş. Bu destek, Unicode veya ANSI karakter oluşturabilirsiniz taşınabilir uygulamaları yazmak kolaylaştırır. Her karakteri bu taşınabilirlik etkinleştirmek için bir `CString` nesne türüdür **TCHAR**, olarak tanımlanan `wchar_t` simgenin tanımlarsanız **_UNICODE** uygulamanızı derlerken veya olarak `char` değilse. A `wchar_t` 16 bit uzunluğunda karakterdir. MBCS simgesiyle yapı etkin **_MBCS** tanımlanmış. MFC'nin biriyle üretilmiştir **_MBCS** simgesi (NAFX kitaplıkları) veya **_UNICODE** tanımlanan simgesi (UAFX kitaplıkları).  
  
> [!NOTE]
>  `CString` Bu örneklerde ve değişmez değer dizeleri için Unicode taşınabilirliği düzgün biçimlendirilmiş dizeler Göster üzerinde eşlik eden makaleler, kullanarak **_T** forma değişmez değer dize çevirir makrosu:  
  
 `L"literal string"`  
  
> [!NOTE]
>  hangi derleyici bir UNICODE dizesi değerlendirir. Örneğin, aşağıdaki kod:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#187](../atl-mfc-shared/codesnippet/cpp/string-data-management_1.cpp)]  
  
> [!NOTE]
>  bir UNICODE dizesi varsa çevrilir **_UNICODE** tanımlı değil veya bir ANSI dizesi değil. Daha fazla bilgi için bkz: [Unicode ve çok baytlı karakter kümesi (MBCS) desteği](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
 A `CString` nesne kadar saklayabilir **INT_MAX** (2.147.483.647) karakter. **TCHAR** veri türü almak veya içindeki tek tek karakterler ayarlamak için kullanılan bir `CString` nesnesi. Karakter dizileri aksine `CString` sınıfı yerleşik bellek ayırma özelliğine sahiptir. Böylece `CString` gerektiğinde otomatik olarak büyümeye nesneleri (diğer bir deyişle, büyüyen hakkında endişelenmeniz gerekmez bir `CString` uzun dizeleri uyacak şekilde nesne).  
  
##  <a name="_core_cstrings_and_const_char_pointers"></a>CStrings ve const char işaretçiler  
 A `CString` nesne de sabit değerli bir C stili dize gibi görev yapabilir (bir `PCXSTR`, aynı olduğu **const char\***  IF Unicode altında değil). [CSimpleStringT::operator PCXSTR](../atl-mfc-shared/reference/csimplestringt-class.md#operator_pcxstr) dönüştürme işleci verir `CString` nesneleri işlev çağrılarında karakter işaretçileri için ücretsiz olarak değiştirdi. **CString (LPCWSTR** `pszSrc` **)** oluşturucusu için değiştirilecek karakter işaretçiler sağlayan `CString` nesneleri.  
  
 Hiçbir denemesi fold yapılan `CString` nesneleri. İki yaparsanız `CString` içeren nesneleri `Chicago`, örneğin, karakterleri `Chicago` iki yerde depolanır. (, Ona bağlı olmaması gerekir böylece bu MFC, gelecek sürümlerinde doğru olmayabilir.)  
  
> [!NOTE]
>  Kullanım [CSimpleStringT::GetBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) ve [CSimpleStringT::ReleaseBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) üye işlevlerini doğrudan erişmek gerektiğinde bir `CString` bir karakter nonconstant işaretçisi olarak.  
  
> [!NOTE]
>  Kullanım [CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring) ve [CStringT::SetSysString](../atl-mfc-shared/reference/cstringt-class.md#setsysstring) ayırmak ve ayarlamak için üye işlevleri `BSTR` (önceki adıyla OLE Otomasyon bilinir) Otomasyonu'ndaki kullanılan nesneleri.  
  
> [!NOTE]
>  Mümkünse, tahsis `CString` nesneleri çerçevesinde yerine yığında. Bu bellek kaydeder ve parametre geçirme basitleştirir.  
  
 `CString` Sınıfı Microsoft Foundation Class Kitaplığı koleksiyon sınıfı, ancak uygulanmadı `CString` nesneleri kesinlikle depolanabilir koleksiyonlarında bulunan öğeleri olarak.  
  
##  <a name="_core_cstring_reference_counting"></a>CString başvuru sayım  
 MFC sürüm 4.0 itibariyle zaman [CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md) nesneleri kopyalanır, MFC verileri kopyalayarak yerine bir başvuru sayısı artar. Bu değer ve parametreleri geçirme kılar `CString` daha verimli değeriyle nesneleri. Bu işlemleri kopya Oluşturucu, bazen birden çok kez çağrılması neden olur. Bu ortak işlemler için bu ek yükünü azaltır ve yapar kullanarak bir başvuru sayısı artan `CString` daha çekici bir seçenek.  
  
 Her kopyası yok gibi özgün nesne başvurusu sayıma düşülür. Özgün `CString` nesne başvuru sayısı sıfır olarak azalana kadar değil yok.  
  
 Kullanabileceğiniz `CString` üye işlevleri [CSimpleStringT::LockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) ve [CSimpleStringT::UnlockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) başvuru sayımı etkinleştirmek veya devre dışı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel MFC konuları](../mfc/general-mfc-topics.md)

