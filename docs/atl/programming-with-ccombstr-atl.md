---
title: CComBSTR (ATL) ile programlama | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CComBSTR class, programming with
- Unicode, using CComBSTR [ATL]
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f8f496dd73c2d15f8f78ddbdc205f31a8520c674
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="programming-with-ccombstr-atl"></a>CComBSTR (ATL) ile programlama
ATL sınıfı [CComBSTR](../atl/reference/ccombstr-class.md) çevresinde bir sarmalayıcı sağlar `BSTR` veri türü. Sırada `CComBSTR` yararlı bir araç olan dikkat gerektiren bazı durumlar vardır.  
  
-   [Dönüştürme sorunları](#programmingwithccombstr_conversionissues)  
  
-   [Kapsam sorunları](#programmingwithccombstr_scopeissues)  
  
-   [Açıkça CComBSTR nesne serbest bırakma](#programmingwithccombstr_explicitlyfreeing)  
  
-   [CComBSTR nesneleri Döngülerde kullanma](#programmingwithccombstr_usingloops)  
  
-   [Bellek sızıntısı sorunları](#programmingwithccombstr_memoryleaks)  
  
##  <a name="programmingwithccombstr_conversionissues"></a>Dönüştürme sorunları  
 Ancak birçok `CComBSTR` yöntemleri otomatik olarak dönüştürme ANSI dize bağımsız değişkeni Unicode'a, yöntem her zaman Unicode biçim dizeleri döndürür. Çıkış dizesi ANSI olarak dönüştürmek için bir ATL dönüştürme sınıfını kullanın. ATL dönüştürme sınıfları hakkında daha fazla bilgi için bkz: [ATL ve MFC dize dönüştürme makrolarını](reference/string-conversion-macros.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/cpp/programming-with-ccombstr-atl_1.cpp)]  
  
 Bir dize sabit değeri değiştirmek için kullanıyorsanız, bir `CComBSTR` nesne, geniş karakter dizelerini kullanın. Bu, gereksiz dönüşümleri azaltır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/cpp/programming-with-ccombstr-atl_2.cpp)]  
  
##  <a name="programmingwithccombstr_scopeissues"></a>Kapsam sorunları  
 Herhangi iyi çalışan bir sınıf olarak ile `CComBSTR` kapsam dışına çıktığında kaynaklarını boşaltır. Bir işlev işaretçisi döndürürse `CComBSTR` dize, bu sorunlara neden olabilir, işaretçi zaten serbest bellek başvurur gibi. Bu gibi durumlarda kullanmak **kopyalama** aşağıda gösterildiği gibi yöntemi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/cpp/programming-with-ccombstr-atl_3.cpp)]  
  
##  <a name="programmingwithccombstr_explicitlyfreeing"></a>Açıkça CComBSTR nesne serbest bırakma  
 İçinde yer alan dize açıkça serbest mümkündür `CComBSTR` kapsam nesne geçmeden önce nesne. Dize serbest, `CComBSTR` nesnesi geçersiz.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/cpp/programming-with-ccombstr-atl_4.cpp)]  
  
##  <a name="programmingwithccombstr_usingloops"></a>CComBSTR nesneleri Döngülerde kullanma  
 Olarak `CComBSTR` sınıfı gibi bazı işlemleri gerçekleştirmek için arabellek ayırır `+=` işleci veya **Append** yöntemi, önerilmez dize düzenlemesi sıkı döngü içinde gerçekleştirin. Bu gibi durumlarda `CStringT` daha iyi performans sağlar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/cpp/programming-with-ccombstr-atl_5.cpp)]  
  
##  <a name="programmingwithccombstr_memoryleaks"></a>Bellek sızıntısı sorunları  
 Başlatılan bir adresini geçirme `CComBSTR` olarak işlev bir **[Çıkış]** parametresi, bir bellek sızıntısı neden olur.  
  
 Aşağıdaki örnekte, dize ayrılmış dize tutmak için `"Initialized"` ne zaman sızmasını işlevi `MyGoodFunction` dizesi yerini alır.  
  
 [!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/cpp/programming-with-ccombstr-atl_6.cpp)]  
  
 Sızıntısını önlemek için arama **boş** varolan yöntemi `CComBSTR` adresi olarak geçirmeden önce nesneleri bir **[Çıkış]** parametresi.  
  
 İşlev parametresi, aynı kod bir sızıntısı neden olmaz olduğunu unutmayın **[ın, out]**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../atl/active-template-library-atl-concepts.md)   
 [CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md)   
 [wstring](../standard-library/basic-string-class.md)   
 [Dize Dönüşüm Makroları](../atl/reference/string-conversion-macros.md)

