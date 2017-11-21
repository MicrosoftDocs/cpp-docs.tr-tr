---
title: "&lt;fstream&gt; tür tanımları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- fstream/std::filebuf
- fstream/std::fstream
- fstream/std::ifstream
- fstream/std::ofstream
- fstream/std::wfilebuf
- fstream/std::wfstream
- fstream/std::wifstream
- fstream/std::wofstream
ms.assetid: 8dddef2d-7f17-42a6-ba08-6f6f20597d23
caps.latest.revision: "11"
manager: ghogen
ms.openlocfilehash: 55a148c472048c5531521cd6f4574477e7c31cac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream&gt; tür tanımları
||||  
|-|-|-|  
|[filebuf](#filebuf)|[fstream](#fstream)|[ifstream](#ifstream)|  
|[ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|  
|[wifstream](#wifstream)|[wofstream](#wofstream)|  
  
##  <a name="filebuf"></a>filebuf  
 Bir tür `basic_filebuf` üzerinde özel `char` şablon parametreleri.  
  
```
typedef basic_filebuf<char, char_traits<char>> filebuf;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı için eş anlamlı türüdür [basic_filebuf](../standard-library/basic-filebuf-class.md), türündeki öğeler için özelleştirilmiş `char` varsayılan karakter nitelikler ile.  
  
##  <a name="fstream"></a>fstream  
 Bir tür `basic_fstream` üzerinde özel `char` şablon parametreleri.  
  
```
typedef basic_fstream<char, char_traits<char>> fstream;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı için eş anlamlı türüdür [basic_fstream](../standard-library/basic-fstream-class.md), türündeki öğeler için özelleştirilmiş `char` varsayılan karakter nitelikler ile.  
  
##  <a name="ifstream"></a>ifstream  
 Tek baytlı karakter verilerini bir dosyadan seri olarak okumak için kullanılacak bir akış tanımlar. `ifstream`Şablon sınıfı uzmanlaşmış bir typedef olan `basic_ifstream` için `char`.  
  
 Ayrıca `wifstream`, uzmanlaşmış bir typedef `basic_ifstream` okumak için `wchar_t` çift genelinde karakter. Daha fazla bilgi için bkz: [wifstream](../standard-library/fstream-typedefs.md#wifstream).  
  
```
typedef basic_ifstream<char, char_traits<char>> ifstream;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı için eş anlamlı türüdür `basic_ifstream`, tür char varsayılan karakter nitelikler ile öğeleri için özelleştirilmiş. Örneğidir  
  
 `using namespace std;`  
  
 `ifstream infile("existingtextfile.txt");`  
  
 `if (!infile.bad())`  
  
 `{`  
  
 `// Dump the contents of the file to cout.`  
  
 `cout << infile.rdbuf();`  
  
 `infile.close();`  
  
 `}`  
  
##  <a name="ofstream"></a>ofstream  
 Bir tür `basic_ofstream` üzerinde özel `char` şablon parametreleri.  
  
```
typedef basic_ofstream<char, char_traits<char>> ofstream;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı için eş anlamlı türüdür [basic_ofstream](../standard-library/basic-ofstream-class.md), türündeki öğeler için özelleştirilmiş `char` varsayılan karakter nitelikler ile.  
  
##  <a name="wfstream"></a>wfstream  
 Bir tür `basic_fstream` üzerinde özel `wchar_t` şablon parametreleri.  
  
```
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı için eş anlamlı türüdür [basic_fstream](../standard-library/basic-fstream-class.md), türündeki öğeler için özelleştirilmiş `wchar_t` varsayılan karakter nitelikler ile.  
  
##  <a name="wifstream"></a>wifstream  
 Bir tür `basic_ifstream` üzerinde özel `wchar_t` şablon parametreleri.  
  
```
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı için eş anlamlı türüdür [basic_ifstream](../standard-library/basic-ifstream-class.md), türündeki öğeler için özelleştirilmiş `wchar_t` varsayılan karakter nitelikler ile.  
  
##  <a name="wofstream"></a>wofstream  
 Bir tür `basic_ofstream` üzerinde özel `wchar_t` şablon parametreleri.  
  
```
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı için eş anlamlı türüdür [basic_ofstream](../standard-library/basic-ofstream-class.md), türündeki öğeler için özelleştirilmiş `wchar_t` varsayılan karakter nitelikler ile.  
  
##  <a name="wfilebuf"></a>wfilebuf  
 Bir tür `basic_filebuf` üzerinde özel `wchar_t` şablon parametreleri.  
  
```
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı için eş anlamlı türüdür [basic_filebuf](../standard-library/basic-filebuf-class.md), türündeki öğeler için özelleştirilmiş `wchar_t` varsayılan karakter nitelikler ile.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<fstream >](../standard-library/fstream.md)



