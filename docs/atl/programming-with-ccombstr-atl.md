---
title: CComBSTR (ATL) ile programlama
ms.date: 11/04/2016
helpviewer_keywords:
- CComBSTR class, programming with
- Unicode, using CComBSTR [ATL]
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
ms.openlocfilehash: 020c2d18c721e658d15bb1451039154ae50b99f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321788"
---
# <a name="programming-with-ccombstr-atl"></a>CComBSTR (ATL) ile programlama

ATL sınıfı [CComBSTR,](../atl/reference/ccombstr-class.md) BSTR veri türü etrafında bir sarmalayıcı sağlar. Yararlı `CComBSTR` bir araç olsa da, dikkatli gerektiren çeşitli durumlar vardır.

- [Dönüşüm Sorunları](#programmingwithccombstr_conversionissues)

- [Kapsam Sorunları](#programmingwithccombstr_scopeissues)

- [CComBSTR Nesnesini Açıkça Serbest Etme](#programmingwithccombstr_explicitlyfreeing)

- [Döngülerde CComBSTR Nesnelerini Kullanma](#programmingwithccombstr_usingloops)

- [Bellek Kaçağı Sorunları](#programmingwithccombstr_memoryleaks)

## <a name="conversion-issues"></a><a name="programmingwithccombstr_conversionissues"></a>Dönüşüm Sorunları

Çeşitli `CComBSTR` yöntemler bir ANSI dize bağımsız değişkenini otomatik olarak Unicode'a dönüştürecek olsa da, yöntemler her zaman Unicode biçimli dizeleri döndürür. Çıktı dizesini ANSI'ye dönüştürmek için Bir ATL dönüştürme sınıfı kullanın. ATL dönüştürme sınıfları hakkında daha fazla bilgi için [ATL ve MFC String Dönüşüm Makroları'na](reference/string-conversion-macros.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/cpp/programming-with-ccombstr-atl_1.cpp)]

Bir `CComBSTR` nesneyi değiştirmek için bir dize literal kullanıyorsanız, geniş karakter dizeleri kullanın. Bu, gereksiz dönüşümleri azaltır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/cpp/programming-with-ccombstr-atl_2.cpp)]

## <a name="scope-issues"></a><a name="programmingwithccombstr_scopeissues"></a>Kapsam Sorunları

Her iyi mizanılsa `CComBSTR` olduğu gibi, kapsam dışına çıktığında kaynaklarını serbest katacak. Bir işlev `CComBSTR` dize için bir işaretçi döndürürse, işaretçi zaten serbest bırakılmış bellek başvurur gibi, bu sorunlara neden olabilir. Bu gibi durumlarda, `Copy` aşağıda gösterildiği gibi yöntemi kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/cpp/programming-with-ccombstr-atl_3.cpp)]

## <a name="explicitly-freeing-the-ccombstr-object"></a><a name="programmingwithccombstr_explicitlyfreeing"></a>CComBSTR Nesnesini Açıkça Serbest Etme

Nesne kapsam dışına çıkmadan önce `CComBSTR` nesnede bulunan dizeyi açıkça serbest kılmak mümkündür. Dize serbest bırakılırsa, `CComBSTR` nesne geçersizdir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/cpp/programming-with-ccombstr-atl_4.cpp)]

## <a name="using-ccombstr-objects-in-loops"></a><a name="programmingwithccombstr_usingloops"></a>Döngülerde CComBSTR Nesnelerini Kullanma

`CComBSTR` Sınıf `+=` işleç veya `Append` yöntem gibi belirli işlemleri gerçekleştirmek için bir arabellek ayırır gibi, sıkı bir döngü içinde dize işleme gerçekleştirmek önerilmez. Bu gibi `CStringT` durumlarda, daha iyi performans sağlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/cpp/programming-with-ccombstr-atl_5.cpp)]

## <a name="memory-leak-issues"></a><a name="programmingwithccombstr_memoryleaks"></a>Bellek Kaçağı Sorunları

[Out] parametresi `CComBSTR` olarak bir **[out]** işlev için başharfe giren bir adresin geçirilmesi bellek sızıntısına neden olur.

Aşağıdaki örnekte, dize tutmak için `"Initialized"` ayrılan dize, `MyGoodFunction` işlev dize yerine zaman sızdırılmış.

[!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/cpp/programming-with-ccombstr-atl_6.cpp)]

Sızıntıyı önlemek için, `Empty` adresi `CComBSTR` **[çıkış]** parametresi olarak geçirmeden önce varolan nesnelerüzerindeki yöntemi arayın.

İşlevin parametresi **[içeri, dışarı]** ise aynı kodun sızıntıya neden olmayacağını unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../atl/active-template-library-atl-concepts.md)<br/>
[CStringT Sınıfı](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[wstring](../standard-library/basic-string-class.md)<br/>
[Dize Dönüşüm Makroları](../atl/reference/string-conversion-macros.md)
