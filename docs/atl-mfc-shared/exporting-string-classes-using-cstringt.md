---
title: CStringT kullanarak dize sınıflarını dışarı aktarma
ms.date: 11/04/2016
helpviewer_keywords:
- CStringT class, exporting strings
ms.assetid: bdfc441e-8d2a-461c-9885-46178066c09f
ms.openlocfilehash: 8c46ae040e64b999c570e99f3bd18cc7d5bc36a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432454"
---
# <a name="exporting-string-classes-using-cstringt"></a>CStringT kullanarak dize sınıflarını dışarı aktarma

Geçmişte, MFC geliştiriciler öğesinden türetilmiş `CString` kendi dize sınıflarını uzmanlaşmıştır. Microsoft Visual C++ .NET (MFC 8.0) içinde [CString](../atl-mfc-shared/using-cstring.md) sınıfı olarak adlandırılan bir şablon sınıfı tarafından değiştirilen [CStringT](../atl-mfc-shared/reference/cstringt-class.md). Bu avantaj sağladı:

- MFC izin `CString` ATL içinde kullanılacak sınıfı projeleri büyük statik kitaplıkta MFC veya DLL bağlama olmadan.

- Yeni `CStringT` özelleştirebileceğiniz Şablon sınıfı, `CString` karakter nitelikleri, C++ Standart Kitaplığı'nda şablonlarına benzer belirtin şablon parametreleri kullanarak davranışı.

- Dışarı aktardığınızda, kendi dize sınıfı kullanarak bir DLL `CStringT`, derleyicinin otomatik olarak dışarı aktarır `CString` temel sınıfı. Bu yana `CString` kendisi bir şablon sınıfıdır, derleyici uyumlu olmadığı sürece, kullanıldığında, derleyici tarafından örneği, `CString` DLL'den içeri aktarılır. Visual C++ .NET için Visual C++ 6.0 projeleri yaptıysanız, size bir Çarp-tanımlanan bağlayıcı sembol hataları görmüş olabilirsiniz `CString` çakışması nedeniyle `CString` DLL ve yerel olarak oluşturulmuş bir sürümü içeri aktarıldı. Bunu yapmak için en uygun yolu aşağıda açıklanmıştır.

Aşağıdaki senaryoda, birden çok kez tanımlanmış sınıfları için Sembol hataları üretmek bağlayıcı neden olur. Dışarı aktardığınız olduğunu varsayalım. bir `CString`-türetilmiş sınıf (`CMyString`) bir MFC uzantılı DLL'nden:

[!code-cpp[NVC_MFC_DLL#6](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_1.cpp)]

Tüketici kod bir karışımını kullanır `CString` ve `CMyString`. Önceden derlenmiş üst bilgi ve bazı kullanımını "MyString.h" dahil değildir `CString` olmayan `CMyString` görünür.

Kullandığını varsayma `CString` ve `CMyString` ayrı kaynak dosyaları, Source1.cpp ve Source2.cpp sınıfları. Kullandığınız Source1.cpp içinde `CMyString` ve # MyString.h include. Kullandığınız Source2.cpp içinde `CString`, ancak olmayan # MyString.h include. Bu durumda, bağlayıcı hakkında şikayet `CStringT` birden çok kez tanımlanmış. Bu kaynaklanır `CString` hem de içe aktaran DLL'den olan `CMyString`ve yerel olarak derleyici tarafından örneği `CStringT` şablonu.

Bu sorunu gidermek için aşağıdakileri yapın:

Dışarı aktarma `CStringA` ve `CStringW` (ve gerekli temel sınıflar) MFC90 öğesinden. DLL. MFC içeren projeleri her zaman dışarı MFC DLL kullanan `CStringA` ve `CStringW`, önceki MFC uygulamalarında gibi.

Dışarı aktarılabilir türetilmiş bir sınıf kullanarak bir oluşturup `CStringT` şablon olarak `CStringT_Exported` , örneğin aşağıdadır:

[!code-cpp[NVC_MFC_DLL#7](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_2.cpp)]

AfxStr.h içinde önceki değiştirin `CString`, `CStringA`, ve `CStringW` aşağıdaki gibi tür tanımları:

[!code-cpp[NVC_MFC_DLL#8](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_3.cpp)]

Bazı uyarılar şunlardır:

- Değil de vermelisiniz `CStringT` kendisi bu özelleştirilmiş dışarı aktarmak yalnızca ATL projeleri neden olacağından `CStringT` sınıfı.

- Dışarı aktarılabilir bir kullanarak sınıfından türetilmiş `CStringT` yeniden uygulamak zorunda en aza indirir `CStringT` işlevselliği. Ek kod oluşturucuları için iletme için sınırlı `CStringT` temel sınıfı.

- `CString`, `CStringA`, ve `CStringW` yalnızca işaretlenmelidir `__declspec(dllexport/dllimport)` ne zaman bir MFC ile oluşturmakta olduğunuz DLL paylaşılan. Bir MFC statik kitaplığı ile bağlantı varsa, bu sınıfları dışarı olarak işaretlemeniz gerekir değil; Aksi takdirde, iç kullanımı `CString`, `CStringA`, ve `CStringW` içinde kullanıcı DLL'leri işaretler `CString` de dışarı gibi.

## <a name="related-topics"></a>İlgili Konular

[CStringT Sınıfı](../atl-mfc-shared/reference/cstringt-class.md)

## <a name="see-also"></a>Ayrıca Bkz.

[CStringT kullanma](../atl-mfc-shared/using-cstringt.md)<br/>
[CString Kullanma](../atl-mfc-shared/using-cstring.md)

