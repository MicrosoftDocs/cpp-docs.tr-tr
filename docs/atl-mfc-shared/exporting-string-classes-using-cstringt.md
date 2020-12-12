---
description: 'Hakkında daha fazla bilgi edinin: CStringT kullanarak dize sınıfları dışarı aktarma'
title: CStringT kullanarak dize sınıflarını dışa aktarma
ms.date: 11/04/2016
helpviewer_keywords:
- CStringT class, exporting strings
ms.assetid: bdfc441e-8d2a-461c-9885-46178066c09f
ms.openlocfilehash: 8876ea04f1252e4f5861a950b04dabcd99d6a804
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166999"
---
# <a name="exporting-string-classes-using-cstringt"></a>CStringT kullanarak dize sınıflarını dışa aktarma

Geçmişte, MFC geliştiricileri `CString` kendi dize sınıflarını özelleştirmek için öğesinden türetilir. Microsoft Visual C++ .NET (MFC 8,0) içinde, [CString](../atl-mfc-shared/using-cstring.md) sınıfının yerini [CStringT](../atl-mfc-shared/reference/cstringt-class.md)adlı bir şablon sınıfı almıştır. Bu, birkaç avantaj sağlamıştır:

- MFC `CString` sınıfının, daha büyük MFC statik kitaplığı veya dll 'ye BAĞLANMADAN ATL projelerinde kullanılmasına izin verilir.

- Yeni `CStringT` şablon sınıfı ile, `CString` C++ standart kitaplığı 'ndaki şablonlara benzer şekilde karakter nitelikleri belirten şablon parametreleri kullanarak davranışı özelleştirebilirsiniz.

- Kullanarak bir DLL 'den kendi dize sınıfınızı dışarı aktardığınızda `CStringT` , derleyici de otomatik olarak temel sınıfı dışarı aktarır `CString` . `CString`Bir şablon sınıfı olduğundan, derleyici `CString` bir dll 'den içeri aktarılan farkında olmadığı takdirde, kullanıldığında derleyici tarafından oluşturulabilir. Projelerini Visual C++ 6,0 ' den Visual C++ .NET 'a geçirdiyseniz, `CString` `CString` bir dll 'den içeri aktarılan ve yerel olarak örneklenen sürümden oluşan çarpışmadan dolayı tanımlanan bir çarpma için bağlayıcı sembol hatalarını görmüş olabilirsiniz. Bunu yapmanın doğru yolu aşağıda açıklanmıştır.

Aşağıdaki senaryo, bağlayıcının tanımlanan sınıfların sembol hatalarını üretmesine neden olur. Bir `CString` `CMyString` MFC uzantı dll 'sinden bir türetilmiş sınıf () dışarı aktardığınız varsayılır:

[!code-cpp[NVC_MFC_DLL#6](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_1.cpp)]

Tüketici kodu ve karışımını kullanır `CString` `CMyString` . "MyString. h" önceden derlenmiş üstbilgiye dahil değildir ve bazı kullanımları `CString` `CMyString` görünür değildir.

`CString`Ve `CMyString` sınıflarını, Source1. cpp ve Source2. cpp ayrı kaynak dosyalarında kullandığınızı varsayalım. Source1. cpp içinde, `CMyString` MyString. h kullanın ve #include. SOURCE2. cpp içinde, `CString` ancak MyString. h #include. Bu durumda, bağlayıcı, `CStringT` tanımlanan Çarpılmakta olan bir şikayet eder. Bu, `CString` hem dışarı AKTARıLAN dll 'den içeri aktarılmakta hem de `CMyString` şablon aracılığıyla derleyici tarafından yerel olarak örneklenmemesinden kaynaklanır `CStringT` .

Bu sorunu gidermek için aşağıdakileri yapın:

`CStringA`MFC90.DLL ve `CStringW` (ve gerekli temel sınıfları) ' dan dışarı aktarın. MFC içeren projeler `CStringA` `CStringW` , önceki MFC uygulamalarında olduğu gibi, ve için her zaman AKTARıLMıŞ MFC DLL 'yi kullanır.

Ardından, aşağıdaki gibi, şablonu kullanarak dışarı aktarılabilir türetilmiş bir sınıf oluşturun `CStringT` `CStringT_Exported` , örneğin:

[!code-cpp[NVC_MFC_DLL#7](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_2.cpp)]

Afxstr. h içinde Previous `CString` , `CStringA` ve tür tanımları ' i `CStringW` aşağıdaki gibi değiştirin:

[!code-cpp[NVC_MFC_DLL#8](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_3.cpp)]

Birkaç uyarılar vardır:

- Kendisini dışarı aktarmamalıdır `CStringT` çünkü bu, yalnızca atl projelerinin özelleştirilmiş bir sınıfı dışarı aktarmaya neden olur `CStringT` .

- Dışarı aktarılabilir türetilmiş bir sınıfın kullanılması, `CStringT` işlevselliği yeniden uygulamak zorunda olan en aza indirir `CStringT` . Ek kod, oluşturucuları temel sınıfa iletme ile sınırlıdır `CStringT` .

- `CString`, `CStringA` , ve `CStringW` yalnızca `__declspec(dllexport/dllimport)` MFC paylaşılan DLL ile derlerken işaretlenmelidir. MFC statik kitaplığıyla bağlantı varsa, bu sınıfları aktarılmış olarak işaretlememelisiniz; Aksi halde,,, `CString` `CStringA` ve `CStringW` Içinde Kullanıcı dll 'lerinin iç kullanımı, olarak da işaretlenir `CString` .

## <a name="related-topics"></a>İlgili Konular

[CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md)

## <a name="see-also"></a>Ayrıca bkz.

[CStringT kullanma](../atl-mfc-shared/using-cstringt.md)<br/>
[CString kullanma](../atl-mfc-shared/using-cstring.md)
