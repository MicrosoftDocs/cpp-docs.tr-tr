---
description: 'Hakkında daha fazla bilgi edinin: CComBSTR (ATL) ile programlama'
title: CComBSTR (ATL) ile programlama
ms.date: 11/04/2016
helpviewer_keywords:
- CComBSTR class, programming with
- Unicode, using CComBSTR [ATL]
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
ms.openlocfilehash: 6c348d703aeaeba40f1f47b8f6fd0ee858b7babd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159225"
---
# <a name="programming-with-ccombstr-atl"></a>CComBSTR (ATL) ile programlama

[CComBSTR](../atl/reference/ccombstr-class.md) ATL sınıfı, BSTR veri türü etrafında bir sarmalayıcı sağlar. `CComBSTR`Faydalı bir araç olsa da dikkat gerektiren birkaç durum vardır.

- [Dönüştürme sorunları](#programmingwithccombstr_conversionissues)

- [Kapsam sorunları](#programmingwithccombstr_scopeissues)

- [CComBSTR nesnesini açık olarak boşaltma](#programmingwithccombstr_explicitlyfreeing)

- [Döngülerde CComBSTR nesneleri kullanma](#programmingwithccombstr_usingloops)

- [Bellek sızıntısı sorunları](#programmingwithccombstr_memoryleaks)

## <a name="conversion-issues"></a><a name="programmingwithccombstr_conversionissues"></a> Dönüştürme sorunları

Birçok `CComBSTR` Yöntem BIR ANSI dize bağımsız değişkenini otomatik olarak Unicode 'a dönüştürecek, ancak Yöntemler her zaman Unicode biçim dizelerini döndürür. Çıktı dizesini tekrar ANSI 'ye dönüştürmek için bir ATL dönüştürme sınıfı kullanın. ATL dönüştürme sınıfları hakkında daha fazla bilgi için bkz. [ATL ve MFC dize dönüştürme makroları](reference/string-conversion-macros.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/cpp/programming-with-ccombstr-atl_1.cpp)]

Bir nesneyi değiştirmek için bir dize sabiti kullanıyorsanız `CComBSTR` , geniş karakter dizeleri kullanın. Bu, gereksiz dönüştürmeleri azaltır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/cpp/programming-with-ccombstr-atl_2.cpp)]

## <a name="scope-issues"></a><a name="programmingwithccombstr_scopeissues"></a> Kapsam sorunları

İyi davranmış sınıfta olduğu gibi, `CComBSTR` kaynakları kapsam dışına geçtiğinde serbest bırakılır. Bir işlev dizeye bir işaretçi döndürürse bu, `CComBSTR` işaretçi zaten serbest bırakılmış belleğe başvurabileceği için soruna neden olabilir. Bu durumlarda, `Copy` yöntemi aşağıda gösterildiği gibi kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/cpp/programming-with-ccombstr-atl_3.cpp)]

## <a name="explicitly-freeing-the-ccombstr-object"></a><a name="programmingwithccombstr_explicitlyfreeing"></a> CComBSTR nesnesini açık olarak boşaltma

Nesne çıkış kapsamından önce nesnede bulunan dizeyi açık bir şekilde serbest bırakmak mümkündür `CComBSTR` . Dize serbest bırakılırsa, `CComBSTR` nesne geçersiz olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/cpp/programming-with-ccombstr-atl_4.cpp)]

## <a name="using-ccombstr-objects-in-loops"></a><a name="programmingwithccombstr_usingloops"></a> Döngülerde CComBSTR nesneleri kullanma

Sınıfı, `CComBSTR` işleç veya yöntem gibi belirli işlemleri gerçekleştirmek için bir arabellek ayırdığında `+=` `Append` , sıkı bir döngü içinde dize düzenleme gerçekleştirmeniz önerilmez. Bu durumlarda, `CStringT` daha iyi performans sağlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/cpp/programming-with-ccombstr-atl_5.cpp)]

## <a name="memory-leak-issues"></a><a name="programmingwithccombstr_memoryleaks"></a> Bellek sızıntısı sorunları

Başlatılmış bir işlevin adresini bir `CComBSTR` **[out]** parametresi olarak geçirmek bellek sızıntısına neden olur.

Aşağıdaki örnekte, `"Initialized"` işlevi dizenin yerini aldığı zaman dizeyi tutacak dize sızdırılacaktır `MyGoodFunction` .

[!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/cpp/programming-with-ccombstr-atl_6.cpp)]

Sızıntıdan kaçınmak için, `Empty` `CComBSTR` adresi bir **[out]** parametresi olarak geçirmeden önce mevcut nesnelerde yöntemi çağırın.

İşlevin parametresi **[in, out]** ise aynı kodun bir sızıntıya neden olamayacağını unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../atl/active-template-library-atl-concepts.md)<br/>
[CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[wstring](../standard-library/basic-string-class.md)<br/>
[Dize dönüştürme makroları](../atl/reference/string-conversion-macros.md)
