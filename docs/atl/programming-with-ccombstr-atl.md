---
title: CComBSTR (ATL) ile programlama
ms.date: 11/04/2016
helpviewer_keywords:
- CComBSTR class, programming with
- Unicode, using CComBSTR [ATL]
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
ms.openlocfilehash: 44689b45d567c524d6db1446cd65201c21499c91
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633122"
---
# <a name="programming-with-ccombstr-atl"></a>CComBSTR (ATL) ile programlama

ATL sınıfı [CComBSTR](../atl/reference/ccombstr-class.md) BSTR veri türü çevresinde bir sarmalayıcı sağlar. Sırada `CComBSTR` faydalı bir araç olan dikkat gerektiren birkaç durum mevcuttur.

- [Dönüştürme sorunları](#programmingwithccombstr_conversionissues)

- [Kapsam sorunları](#programmingwithccombstr_scopeissues)

- [CComBSTR nesne açıkça serbest bırakma](#programmingwithccombstr_explicitlyfreeing)

- [Döngülerde CComBSTR nesnelerini kullanma](#programmingwithccombstr_usingloops)

- [Bellek sızıntısı sorunları](#programmingwithccombstr_memoryleaks)

##  <a name="programmingwithccombstr_conversionissues"></a> Dönüştürme sorunları

Ancak birkaç `CComBSTR` yöntemleri tarafından otomatik olarak dönüştürülür ANSI dize bağımsız değişken Unicode, yöntemleri her zaman Unicode biçim dizeler döndürecektir. ANSI-çıkış dizesi dönüştürmek için bir ATL dönüştürme sınıfı kullanın. ATL dönüştürme sınıfları hakkında daha fazla bilgi için bkz. [ATL ve MFC dize dönüşüm makroları](reference/string-conversion-macros.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/cpp/programming-with-ccombstr-atl_1.cpp)]

Değiştirilecek dize değişmez değeri kullanıyorsanız bir `CComBSTR` nesne, geniş karakter dizeleri kullanın. Bu, gereksiz dönüştürmeler azaltır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/cpp/programming-with-ccombstr-atl_2.cpp)]

##  <a name="programmingwithccombstr_scopeissues"></a> Kapsam sorunları

Tüm iyi çalışan sınıfı ile `CComBSTR` kapsam dışına çıktığında kaynaklarıyla boşaltır. Bir işlev işaretçisi döndürürse `CComBSTR` dize, bu sorunlara neden olabilir, işaretçi serbest bırakılmış bellek Bakacağınız gibi. Bu gibi durumlarda kullanmak `Copy` aşağıda gösterildiği gibi yöntemi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/cpp/programming-with-ccombstr-atl_3.cpp)]

##  <a name="programmingwithccombstr_explicitlyfreeing"></a> CComBSTR nesne açıkça serbest bırakma

İçindeki dize açıkça serbest mümkündür `CComBSTR` nesne kapsam geçmeden önce nesne. Dize serbest bırakılır, `CComBSTR` nesnesi geçersiz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/cpp/programming-with-ccombstr-atl_4.cpp)]

##  <a name="programmingwithccombstr_usingloops"></a> Döngülerde CComBSTR nesnelerini kullanma

Olarak `CComBSTR` sınıfı gibi belirli işlemleri gerçekleştirmek için bir arabelleği ayırır `+=` işleci veya `Append` yöntemi önerilmez sıkı bir döngü içinde dize işlemleri gerçekleştirin. Bu gibi durumlarda `CStringT` daha iyi performans sağlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/cpp/programming-with-ccombstr-atl_5.cpp)]

##  <a name="programmingwithccombstr_memoryleaks"></a> Bellek sızıntısı sorunları

Başlatılan bir adresi geçirme `CComBSTR` işlevi görecek bir **[out]** parametresi, bir bellek sızıntısı neden olur.

Aşağıdaki örnekte, dize ayrılmış dizesini tutan `"Initialized"` ne zaman sızmış işlevi `MyGoodFunction` dize değiştirir.

[!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/cpp/programming-with-ccombstr-atl_6.cpp)]

Sızıntısını önlemek için çağrı `Empty` mevcut yöntemi `CComBSTR` adresi olarak geçirmeden önce nesneleri bir **[out]** parametresi.

İşlev parametresi varsa aynı kodu sızıntı neden olmaz, Not **[içinde out]**.

## <a name="see-also"></a>Ayrıca Bkz.

[Kavramları](../atl/active-template-library-atl-concepts.md)<br/>
[CStringT Sınıfı](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[wstring](../standard-library/basic-string-class.md)<br/>
[Dize Dönüşüm Makroları](../atl/reference/string-conversion-macros.md)

