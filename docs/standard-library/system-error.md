---
title: '&lt;system_error&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <system_error>
- system_error
dev_langs: C++
helpviewer_keywords: system_error header
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7869ba251868241c082080d3485d5a82c492b8f3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltsystemerrorgt"></a>&lt;system_error&gt;
Üstbilgisini `<system_error>` özel durum sınıfı tanımlamak için `system_error` ve ilgili alt düzey sistem hataları işlemek için şablonlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <system_error>  
```  
  
### <a name="objects"></a>Nesneler  
  
|||  
|-|-|  
|[generic_category](../standard-library/system-error-functions.md#generic_category)|Genel hataları kategorisini temsil eder.|  
|[system_category](../standard-library/system-error-functions.md#system_category)|Alt düzey sistem taşan tarafından kaynaklanan hataları kategorisini temsil eder.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[generic_errno](../standard-library/system-error-typedefs.md#generic_errno)|POSIX içinde tanımlanan tüm hata kodu makroları simgesel adları sağlar numaralandırması temsil eden bir tür `<errno.h>`.|  
  
### <a name="functions"></a>İşlevler  
  
|||  
|-|-|  
|[make_error_code](../standard-library/system-error-functions.md#make_error_code)|Oluşturur bir `error_code` nesne.|  
|[make_error_condition](../standard-library/system-error-functions.md#make_error_condition)|Oluşturur bir `error_condition` nesne.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator ==](../standard-library/system-error-operators.md#op_eq_eq)|Nesne işlecinin sol tarafındaki sağ tarafında nesnesine eşitse testleri.|  
|[operator! =](../standard-library/system-error-operators.md#op_neq)|Testleri işlecinin sol tarafındaki nesnesi sağ tarafında nesnede eşit değil.|  
|[operator <](../standard-library/system-error-operators.md#op_lt)|Bir nesnenin karşılaştırma için içeri geçirilen nesneden küçük olup olmadığını sınar.|  
  
### <a name="enumerations"></a>Numaralandırmalar  
  
|||  
|-|-|  
|[errc](../standard-library/system-error-enums.md#errc)|POSIX içinde tanımlanan tüm hata kodu makroları için sembolik adlarını sağlar `<errno.h>`.|  
  
### <a name="classes-and-structs"></a>Sınıflar ve Yapılar  
  
|||  
|-|-|  
|[error_category](../standard-library/error-category-class.md)|Nesneler için hata kodları kategorisini tanımlayan soyut, ortak tabanı temsil eder.|  
|[error_code](../standard-library/error-code-class.md)|Uygulamaya özel alt düzey sistem hataları temsil eder.|  
|[error_condition](../standard-library/error-condition-class.md)|Kullanıcı tanımlı hata kodları temsil eder.|  
|[is_error_code_enum](../standard-library/is-error-code-enum-class.md)|İçin test türü koşulu temsil eden [error_code sınıfı](../standard-library/error-code-class.md) numaralandırması.|  
|[is_error_condition_enum](../standard-library/is-error-condition-enum-class.md)|İçin test türü koşulu temsil eden [error_condition sınıfı](../standard-library/error-condition-class.md) numaralandırması.|  
|[system_error](../standard-library/system-error-class.md)|Bir alt düzey sistem taşması bildirmek için oluşturulan tüm özel durumlar için temel sınıfı temsil eder.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<system_error >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)



