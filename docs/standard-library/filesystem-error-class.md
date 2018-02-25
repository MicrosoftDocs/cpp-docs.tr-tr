---
title: "filesystem_error sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
dev_langs:
- C++
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 764be5467282b04e4cd7fa13ee44fddee7c0a51b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="filesystemerror-class"></a>filesystem_error Sınıfı
Bir alt düzey sistem taşması bildirmek için oluşturulan tüm özel durumlar için temel sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class filesystem_error    : public system_error;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir hatayı bildirmek için oluşturulan tüm özel durumlar için temel sınıf sınıfı gören \<filesystem > işlevleri. Burada mymesg exposition amaçları doğrultusunda adlı dize türünde bir nesne depolar. Ayrıca, iki tür yolu, mypval1 ve mypval2 adlı nesnelerin depolar.  
  
## <a name="filesystemerrorfilesystemerror"></a>filesystem_error::filesystem_error  
  
```  
filesystem_error(const string& what_arg,
    error_code ec);

filesystem_error(const string& what_arg,  
    const path& pval1,
    error_code ec);

filesystem_error(const string& what_arg,  
    const path& pval1,
    const path& pval2,
    error_code ec);
```  
  
 Kendi ileti what_arg ve bilinmekteydi. ilk Oluşturucusu oluşturur İkinci Oluşturucu, ayrıca kendi içinde mypval1 depolar pval1 iletiden oluşturur. Üçüncü Oluşturucusu Ayrıca kendi ileti mypval1 içinde depolar, pval1 ve mypval2 içinde depolar pval2 oluşturur.  
  
## <a name="filesystemerrorpath1"></a>filesystem_error::path1  
  
```  
const path& path1() const noexcept;  
```  
  
 Üye işlevini mypval1 döndürür  
  
## <a name="filesystemerrorpath2"></a>filesystem_error::path2  
  
```  
const path& path2() const noexcept;  
```  
  
 Üye işlevini mypval2 döndürür  
  
## <a name="filesystemerrorwhat"></a>filesystem_error::what  
  
```  
const char *what() const noexcept;  
```  
  
 Üye işlevi bir işaretçi tercihen runtime_error::what(), system_error::what(), mymesg, mypval1.native_string() ve mypval2.native_string() oluşan bir NTBS döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<filesystem >  
  
 **Namespace:** std::experimental::filesystem  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [system_error sınıfı](../standard-library/system-error-class.md)   
 [\<filesystem>](../standard-library/filesystem.md)   
 [\<Özel Durum >](../standard-library/exception.md)

