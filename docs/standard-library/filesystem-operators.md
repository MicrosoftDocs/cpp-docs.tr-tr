---
title: "&lt;dosya sistemi&gt; işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FILESYSTEM/std::experimental::filesystem::operator==
- FILESYSTEM/std::experimental::filesystem::operator!=
- FILESYSTEM/std::experimental::filesystem::operator<
- FILESYSTEM/std::experimental::filesystem::operator<=
- FILESYSTEM/std::experimental::filesystem::operator>
- FILESYSTEM/std::experimental::filesystem::operator>=
- FILESYSTEM/std::experimental::filesystem::operator/
- FILESYSTEM/std::experimental::filesystem::operator<<
- FILESYSTEM/std::experimental::filesystem::operator>>
dev_langs: C++
ms.assetid: 102c4833-aa3b-41a8-8998-f5003c546bfd
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 815ff0025372e8b085f7c6f6ea38299bb15c8305
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ltfilesystemgt-operators"></a>&lt;dosya sistemi&gt; işleçleri
İşleçler iki yolu sözcük karşılaştırması dize olarak gerçekleştirin. Kullanım **eşdeğer** iki yolu (örneğin, göreli bir yol ve mutlak bir yol) aynı dosya veya dizin diskteki başvurmak olup olmadığını belirlemek için işlev.  
  
```  
C:\root> D:\root: false  
C:\root> C:\root\sub: false  
C:\root> C:\roo: true  
```  
  
 Daha fazla bilgi için bkz: [dosya sistemi Gezinti (C++)](../standard-library/file-system-navigation.md).  
  
## <a name="operator"></a>operator==  
  
```  
bool operator==(const path& left, const path& right) noexcept;  
```  
  
 Left.native() işlevi döndürür right.native() ==.  
  
## <a name="operator"></a>operator!=  
  
```  
bool operator!=(const path& left, const path& right) noexcept;  
```  
  
 İşlev verir! (sağdan sola ==).  
  
## <a name="operator"></a>operator<  
  
```  
bool operator<(const path& left, const path& right) noexcept;  
```  
  
 Left.native() işlevi döndürür < right.native().  
  
## <a name="operator"></a>operator<=  
  
```  
bool operator<=(const path& left, const path& right) noexcept;  
```  
  
 İşlev verir! (sağ \< sol).  
  
## <a name="operator"></a>operator >  
  
```  
bool operator>(const path& left, const path& right) noexcept;  
```  
  
 İşlev sağa döndürür \< sol.  
  
## <a name="operator"></a>operator > =  
  
```  
bool operator>=(const path& left, const path& right) noexcept;  
```  
  
 İşlev verir! (sol < sağ).  
  
## <a name="operator"></a>operator /  
  
```  
path operator/(const path& left, const path& right);
```  
  
 İşlev çalıştırır:  
  
```  
basic_string<Elem, Traits> str;  
path ans = left;  
return (ans /= right);
```  
  
## <a name="operator"></a>işleç <<  
  
```  
template <class Elem, class Traits>  
basic_ostream<Elem, Traits>& operator<<(basic_ostream<Elem, Traits>& os, const path& pval);
```  
  
 İşletim sistemi işlevi döndürür << pval.string\<Elem, nitelikler > ().  
  
## <a name="operator"></a>İşleç >>  
  
```  
template <class Elem, class Traits>  
basic_istream<Elem, Traits>& operator<<(basic_istream<Elem, Traits>& is, const path& pval);
```  
  
 İşlev çalıştırır:  
  
```  
basic_string<Elem, Traits> str;  
is>> str;  
pval = str;  
return (is);
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [PATH sınıfı (Standart C++ Kitaplığı)](../standard-library/path-class.md)   
 [Dosya sistemi gezintisi (C++)](../standard-library/file-system-navigation.md)   
 [\<FileSystem >](../standard-library/filesystem.md)

