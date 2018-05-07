---
title: CSQLLanguages, Csqllanguageınfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSQLLanguageInfo
- m_szProgrammingLanguage
- m_szImplementation
- m_szIntegrity
- m_szBindingStyle
- m_szConformance
- m_szSource
- m_szYear
- CSQLLanguages
dev_langs:
- C++
helpviewer_keywords:
- m_szBindingStyle
- m_szProgrammingLanguage
- m_szYear
- m_szImplementation
- m_szSource
- m_szConformance
- CSQLLanguages typedef class
- CSQLLanguageInfo parameter class
- m_szIntegrity
ms.assetid: 9c36c5bb-6917-49c3-9ac3-942339893f19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 214cd5b1a4554d90ac21a87aad0951a21126af4d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="csqllanguages-csqllanguageinfo"></a>CSQLLanguages, CSQLLanguageInfo
Çağrı typedef sınıfı **CSQLLanguages** parametre sınıfı uygulamak için **Csqllanguageınfo**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [şema satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) typedef sınıfları kullanma hakkında daha fazla bilgi için.  
  
 Bu sınıf Uyumluluk Düzeyleri, seçenekleri ve SQL uygulaması işleme veri Kataloğu'nda tanımlanan tarafından desteklenen Portekizce tanımlar.  
  
 Aşağıdaki tabloda, sınıf veri üyeleri ve bunların karşılık gelen OLE DB sütunlarını listeler. Bkz: [SQL_LANGUAGES satır kümesi](https://msdn.microsoft.com/en-us/library/ms714374.aspx) içinde *OLE DB Programcının Başvurusu* şemayı ve sütunları hakkında daha fazla bilgi.  
  
|Veri üyeleri|OLE DB sütunları|  
|------------------|--------------------|  
|m_szSource|SQL_LANGUAGE_SOURCE|  
|m_szYear|SQL_LANGUAGE_YEAR|  
|m_szConformance|SQL_LANGUAGE_CONFORMANCE|  
|m_szIntegrity|SQL_LANGUAGE_INTEGRITY|  
|m_szImplementation|SQL_LANGUAGE_IMPLEMENTATION|  
|m_szBindingStyle|SQL_LANGUAGE_BINDING_STYLE|  
|m_szProgrammingLanguage|SQL_LANGUAGE_PROGRAMMING_LANGUAGE|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbsch.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRestrictions Sınıfı](../../data/oledb/crestrictions-class.md)