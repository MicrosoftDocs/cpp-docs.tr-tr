---
title: "directory_entry sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- filesystem/std::experimental::filesystem::directory_entry::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator=
- filesystem/std::experimental::filesystem::directory_entry::assign
- filesystem/std::experimental::filesystem::directory_entry::replace_filename
- filesystem/std::experimental::filesystem::directory_entry::path
- filesystem/std::experimental::filesystem::directory_entry::status
- filesystem/std::experimental::filesystem::directory_entry::symlink_status
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;
- filesystem/std::experimental::filesystem::directory_entry::operator==
- filesystem/std::experimental::filesystem::directory_entry::operator!=
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;=
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;=
dev_langs:
- C++
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::experimental::filesystem::directory_entry
- std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- std::experimental::filesystem::directory_entry::directory_entry
- std::experimental::filesystem::directory_entry::operator=
- std::experimental::filesystem::directory_entry::assign
- std::experimental::filesystem::directory_entry::replace_filename
- std::experimental::filesystem::directory_entry::path
- std::experimental::filesystem::directory_entry::status
- std::experimental::filesystem::directory_entry::symlink_status
- std::experimental::filesystem::directory_entry::operator&lt;
- std::experimental::filesystem::directory_entry::operator==
- std::experimental::filesystem::directory_entry::operator!=
- std::experimental::filesystem::directory_entry::operator&lt;=
- std::experimental::filesystem::directory_entry::operator&gt;
- std::experimental::filesystem::directory_entry::operator&gt;=
ms.workload:
- cplusplus
ms.openlocfilehash: d47120c49f63339f0b7eea5be109a3b52d627d72
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="directoryentry-class"></a>directory_entry Sınıfı
Tarafından döndürülen bir nesneyi tanımlayan `*X`, burada *X* olan bir [directory_iterator](../standard-library/directory-iterator-class.md) veya [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class directory_entry;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıf türünde bir nesne depolar [yolu](../standard-library/path-class.md). Saklı `path` bir örneği olabilir [path sınıfı](../standard-library/path-class.md) veya türetilmiş bir tür `path`. İki de depolar [file_type](../standard-library/filesystem-enumerations.md#file_type) değerleri; depolanan dosya adı durumu hakkında bilinen temsil eden, diğeri, dosya adı sembolik bağlantıyı durumu hakkında bilinen temsil eder.  
  
 Daha fazla bilgi ve kod örnekleri için bkz: [dosya sistemi Gezinti (C++)](../standard-library/file-system-navigation.md).  
  
## <a name="assign"></a>Ata  
  
```  
void assign(const std::experimental::filesystem::path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());
```  
  
 Üye işlevini pval YOLUM, mystat stat ve mysymstat symstat atar.  
  
## <a name="directoryentry"></a>directory_entry  
  
```  
directory_entry() = default;  
directory_entry(const directory_entry&) = default;  
directory_entry(directory_entry&&) noexcept = default;  
explicit directory_entry(const std::experimental::filesystem::path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());
```  
  
 Varsayılan oluşturucular beklendiği gibi davranır. Dördüncü Oluşturucu pval YOLUM, stat_arg mystat ve symstat_arg mysymstat başlatır.  
  
## <a name="operator"></a>operator!=  
  
```  
bool operator!=(const directory_entry& right) const noexcept;  
```  
  
 Üye işlevini verir! (* Bu sağ ==).  
  
## <a name="operator"></a>operator=  
  
```  
directory_entry& operator=(const directory_entry&) = default;  
directory_entry& operator=(directory_entry&&) noexcept = default;  
```  
  
 Varsayılan üye atama işleçleri beklendiği gibi davranır.  
  
## <a name="operator"></a>operator==  
  
```  
bool operator==(const directory_entry& right) const noexcept;  
```  
  
 Üye işlevini YOLUM döndürür right.mypath ==.  
  
## <a name="operatorlt"></a>işleci&lt;  
  
```  
bool operator<(const directory_entry& right) const noexcept;  
```  
  
 Üye işlevini YOLUM döndürür &lt; right.mypath.  
  
## <a name="operatorlt"></a>işleci&lt;=  
  
```  
bool operator&lt;=(const directory_entry& right) const noexcept;  
```  
  
 Üye işlevini verir! (sağ \< * bu).  
  
## <a name="operatorgt"></a>işleci&gt;  
  
```  
bool operator&gt;(const directory_entry& right) const noexcept;  
```  
  
 Üye işlevini sağa döndürür \< * bu.  
  
## <a name="operatorgt"></a>işleci&gt;=  
  
```  
bool operator&gt;=(const directory_entry& right) const noexcept;  
```  
  
 Üye işlevini verir! (* Bu \< sağ).  
  
## <a name="operator-const-pathtype"></a>İşleç const path_type &  
  
``` 
 operator const std::experimental::filesystem::path&() const; 
```  
  
 Üye işleci YOLUM döndürür.  
  
## <a name="path"></a>yol  
  
```  
const std::experimental::filesystem::path& path() const noexcept;  
```  
  
 Üye işlevini YOLUM döndürür.  
  
## <a name="replacefilename"></a>replace_filename  
  
```  
void replace_filename(
    const std::experimental::filesystem::path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());
```  
  
 Üye işlevini YOLUM mypath.parent_path() ile değiştirir. / pval, stat_arg ile mystat ve mysymstat symstat_arg ile  
  
## <a name="status"></a>durum  
  
```  
file_status status() const; 
file_status status(error_code& ec) const noexcept;  
```  
  
 Her iki üye işlevleri büyük olasılıkla ilk şu şekilde değiştirilmiş mystat döndürün:  
  
1.  Status_known(mystat) sonra hiçbir şey yapma varsa.  
  
2.  Aksi halde, eğer! status_known(mysymstat) & &! is_symlink(mysymstat) sonra mystat mysymstat =.  
  
## <a name="symlinkstatus"></a>symlink_status  
  
```  
file_status symlink_status() const; 
file_status symlink_status(error_code& ec) const noexcept;  
```  
  
 Her iki üye işlevleri büyük olasılıkla ilk aşağıdaki: If status_known(mysymstat) değiştirilmiş mysymstat dönün sonra hiçbir şey yapma. Aksi takdirde mysymstat symlink_status(mypval) =.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<Deneysel/dosya sistemi&gt;  
  
 **Namespace:** std::experimental::filesystem  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem&gt;](../standard-library/filesystem.md)

