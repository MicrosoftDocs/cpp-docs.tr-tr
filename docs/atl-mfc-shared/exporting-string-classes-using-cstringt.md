---
title: CStringT kullanarak dize sınıfları dışarı aktarma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CStringT class, exporting strings
ms.assetid: bdfc441e-8d2a-461c-9885-46178066c09f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7510b1f44f49d17211c71419f4dde5a6e6a78974
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356402"
---
# <a name="exporting-string-classes-using-cstringt"></a>CStringT kullanarak dize sınıfları dışarı aktarma
Geçmişte, MFC geliştiriciler türetilmiş `CString` kendi dize sınıfları özelleştirmek üzere. Microsoft Visual C++ .NET (MFC 8.0) içinde [CString](../atl-mfc-shared/using-cstring.md) sınıfı olarak adlandırılan bir şablon sınıfı tarafından değiştirilen [CStringT](../atl-mfc-shared/reference/cstringt-class.md). Bu, birkaç avantaj sağlanan:  
  
-   MFC izin `CString` ATL içinde kullanılacak sınıfı projeleri büyük MFC statik kitaplık ya da DLL bağlamadan.  
  
-   Yeni `CStringT` Şablon sınıfı özelleştirebilirsiniz `CString` karakter nitelikler, C++ Standart Kitaplığı şablonlarında benzer belirtin şablon parametrelerini kullanarak davranışı.  
  
-   Kullanarak bir DLL kendi string sınıfı aktardığınızda `CStringT`, derleyici da otomatik olarak dışa aktarır `CString` temel sınıfı. Bu yana `CString` kendisini bir şablon sınıfı olan derleyici farkında olmadığı sürece, kullanıldığında, derleyici tarafından örneği oluşturulabilir, `CString` DLL'den dışarı aktarılır. Visual C++ .NET projeleri Visual C++ 6.0 geçiş yaptıysanız, bağlayıcı simgesi hatalarını bir Çarp tanımlı için gördüğünüz `CString` çakışması nedeniyle `CString` DLL ve yerel olarak oluşturulmuş sürümü alma işlemi. Bunu yapmak için uygun şekilde aşağıda açıklanmıştır. Bilgi Bankası makalesi, bu sorunla ilgili daha fazla bilgi için bkz: "CString türetilmiş içeri aktardığınızda bağlama hataları sınıfları" (Q309801) adresindeki [ http://support.microsoft.com/default.aspx ](http://support.microsoft.com/default.aspx).  
  
 Aşağıdaki senaryoyu Çarp tanımlanan sınıflar için simge hataları üretmek bağlayıcı neden olur. Verdiğiniz olduğunu varsayın bir `CString`-türetilen sınıfı (`CMyString`) bir MFC uzantı DLL:  
  
 [!code-cpp[NVC_MFC_DLL#6](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_1.cpp)]  
  
 Tüketici kodu bir karışımını kullanan `CString` ve `CMyString`. Önceden derlenmiş üst bilgi ve bazı kullanımı "MyString.h" dahil edilmemiştir `CString` sahip olmayan `CMyString` görünür.  
  
 Kullandığınızı varsayar `CString` ve `CMyString` ayrı bir kaynak dosyaları, Source1.cpp ve Source2.cpp sınıfları. Kullandığınız Source1.cpp içinde `CMyString` ve # MyString.h include. Kullandığınız Source2.cpp içinde `CString`, ancak sağlamadığı # MyString.h include. Bu durumda, bağlayıcı hakkında şikayetçi `CStringT` birden çok kez tanımlanmış. Bunun nedeni `CString` her ikisi de içe aktaran DLL'den olan `CMyString`ve derleyicide tarafından yerel olarak örneği `CStringT` şablonu.  
  
 Bu sorunu gidermek için aşağıdakileri yapın:  
  
 Dışarı aktarma `CStringA` ve `CStringW` (ve gerekli temel sınıflar) MFC90 gelen. DLL. MFC dahil projeleri her zaman dışarı MFC DLL kullan `CStringA` ve `CStringW`, önceki MFC uygulamalarında gibi.  
  
 Kullanarak bir verilebilir türetilmiş sınıf oluşturmak `CStringT` şablon olarak `CStringT_Exported` , örneğin aşağıdadır:  
  
 [!code-cpp[NVC_MFC_DLL#7](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_2.cpp)]  
  
 AfxStr.h içinde önceki Değiştir `CString`, `CStringA`, ve `CStringW` şekilde tür tanımları:  
  
 [!code-cpp[NVC_MFC_DLL#8](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_3.cpp)]  
  
 Birkaç uyarılar vardır:  
  
-   Değil vermelisiniz `CStringT` kendisini bu özel dışarı aktarmak yalnızca ATL projeleri neden olacağından `CStringT` sınıfı.  
  
-   Sınıfından türetilen bir verilebilir kullanarak `CStringT` yeniden uygulamak zorunda en aza indirir `CStringT` işlevselliği. Ek kod oluşturucuları için iletme için sınırlı `CStringT` temel sınıfı.  
  
-   `CString`, `CStringA`, ve `CStringW` yalnızca işaretlenmelidir `__declspec(dllexport/dllimport)` paylaşılan DLL ne zaman bir MFC ile oluşturma. Bir MFC statik kitaplığı ile bağlantı varsa, bu sınıfları dışarı olarak işaretlemeniz gerekir değil; Aksi takdirde, iç kullanımını `CString`, `CStringA`, ve `CStringW` kullanıcı DLL'leri içinde işaretler `CString` de dışarı gibi.  
  
## <a name="related-topics"></a>İlgili Konular  
 [CStringT Sınıfı](../atl-mfc-shared/reference/cstringt-class.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStringT kullanma](../atl-mfc-shared/using-cstringt.md)   
 [CString Kullanma](../atl-mfc-shared/using-cstring.md)

