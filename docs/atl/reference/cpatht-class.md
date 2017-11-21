---
title: "CPathT sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPathT
- ATLPATH/ATL::CPathT
- ATLPATH/ATL::CPathT::PCXSTR
- ATLPATH/ATL::CPathT::PXSTR
- ATLPATH/ATL::CPathT::XCHAR
- ATLPATH/ATL::CPathT::CPathT
- ATLPATH/ATL::CPathT::AddBackslash
- ATLPATH/ATL::CPathT::AddExtension
- ATLPATH/ATL::CPathT::Append
- ATLPATH/ATL::CPathT::BuildRoot
- ATLPATH/ATL::CPathT::Canonicalize
- ATLPATH/ATL::CPathT::Combine
- ATLPATH/ATL::CPathT::CommonPrefix
- ATLPATH/ATL::CPathT::CompactPath
- ATLPATH/ATL::CPathT::CompactPathEx
- ATLPATH/ATL::CPathT::FileExists
- ATLPATH/ATL::CPathT::FindExtension
- ATLPATH/ATL::CPathT::FindFileName
- ATLPATH/ATL::CPathT::GetDriveNumber
- ATLPATH/ATL::CPathT::GetExtension
- ATLPATH/ATL::CPathT::IsDirectory
- ATLPATH/ATL::CPathT::IsFileSpec
- ATLPATH/ATL::CPathT::IsPrefix
- ATLPATH/ATL::CPathT::IsRelative
- ATLPATH/ATL::CPathT::IsRoot
- ATLPATH/ATL::CPathT::IsSameRoot
- ATLPATH/ATL::CPathT::IsUNC
- ATLPATH/ATL::CPathT::IsUNCServer
- ATLPATH/ATL::CPathT::IsUNCServerShare
- ATLPATH/ATL::CPathT::MakePretty
- ATLPATH/ATL::CPathT::MatchSpec
- ATLPATH/ATL::CPathT::QuoteSpaces
- ATLPATH/ATL::CPathT::RelativePathTo
- ATLPATH/ATL::CPathT::RemoveArgs
- ATLPATH/ATL::CPathT::RemoveBackslash
- ATLPATH/ATL::CPathT::RemoveBlanks
- ATLPATH/ATL::CPathT::RemoveExtension
- ATLPATH/ATL::CPathT::RemoveFileSpec
- ATLPATH/ATL::CPathT::RenameExtension
- ATLPATH/ATL::CPathT::SkipRoot
- ATLPATH/ATL::CPathT::StripPath
- ATLPATH/ATL::CPathT::StripToRoot
- ATLPATH/ATL::CPathT::UnquoteSpaces
- ATLPATH/ATL::CPathT::m_strPath
dev_langs: C++
helpviewer_keywords: CPathT class
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c9abb6a20beca39e8224ab3d3724da9664f68702
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cpatht-class"></a>CPathT sınıfı
Bu sınıf bir yolunu temsil eder.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename StringType>
class CPathT
```  
  
#### <a name="parameters"></a>Parametreler  
 `StringType`  
 Yol için kullanılacak ATL/MFC string sınıfı (bkz [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)).  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPathT::PCXSTR](#pcxstr)|Bir sabit dize türü.|  
|[CPathT::PXSTR](#pxstr)|Bir dize türü.|  
|[CPathT::XCHAR](#xchar)|Bir karakter türü.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPathT::CPathT](#cpatht)|Yolun Oluşturucusu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPathT::AddBackslash](#addbackslash)|Eğik bir yolu doğru sözdizimi oluşturmak için bir dize sonu eklemek için bu yöntemi çağırın.|  
|[CPathT::AddExtension](#addextension)|Bir dosya uzantısı için bir yol eklemek için bu yöntemi çağırın.|  
|[CPathT::Append](#append)|Geçerli yolu bir dize eklemek için bu yöntemi çağırın.|  
|[CPathT::BuildRoot](#buildroot)|Belirtilen sürücü numarasından kök yolu oluşturmak için bu yöntemi çağırın.|  
|[CPathT::Canonicalize](#canonicalize)|Kurallı biçimi yolu dönüştürmek için bu yöntemi çağırın.|  
|[CPathT::Combine](#combine)|Bir dizin adı temsil eden bir dize ve bir dosya yolu adı tek bir yol temsil eden bir dize birleştirmek için bu yöntemi çağırın.|  
|[CPathT::CommonPrefix](#commonprefix)|Belirtilen yol geçerli yoluna sahip ortak bir önek paylaşır olup olmadığını belirlemek için bu yöntemi çağırın.|  
|[CPathT::CompactPath](#compactpath)|Üç nokta ile yol bileşenlerini değiştirerek içinde verilen piksel genişliği sığması için bir dosya yolu kesmek için bu yöntemi çağırın.|  
|[CPathT::CompactPathEx](#compactpathex)|Üç nokta ile yol bileşenlerini değiştirerek belirli sayıda karakteri içinde sığması için bir dosya yolu kesmek için bu yöntemi çağırın.|  
|[CPathT::FileExists](#fileexists)|Bu yol adı konumundaki dosya var olup olmadığını denetlemek için bu yöntemi çağırın.|  
|[CPathT::FindExtension](#findextension)|Dosya uzantısı yolu içindeki konumunu bulmak için bu yöntemi çağırın.|  
|[CPathT::FindFileName](#findfilename)|Yol dosya adını konumunu bulmak için bu yöntemi çağırın.|  
|[CPathT::GetDriveNumber](#getdrivenumber)|'A'-'Z' aralığında bir sürücü harfi yolu arayın ve karşılık gelen sürücü sayı döndürmek için bu yöntemi çağırın.|  
|[CPathT::GetExtension](#getextension)|Dosya uzantısı yolundan almak için bu yöntemi çağırın.|  
|[CPathT::IsDirectory](#isdirectory)|Yolun geçerli bir dizin olup olmadığını denetlemek için bu yöntemi çağırın.|  
|[CPathT::IsFileSpec](#isfilespec)|Yol sınırlandırma karakterler için bir yol aramak için bu yöntemi çağırın (örneğin, ':' veya '\\'). Mevcut hiçbir yolu ayıran karakter varsa, yol dosya Spec yolu olarak kabul edilir.|  
|[CPathT::IsPrefix](#isprefix)|Bir yol geçirilen türü geçerli bir önek içerip içermediğini belirlemek için bu yöntemi çağırın `pszPrefix`.|  
|[CPathT::IsRelative](#isrelative)|Yolun göreli olup olmadığını belirlemek için bu yöntemi çağırın.|  
|[CPathT::IsRoot](#isroot)|Yol bir dizin kök olup olmadığını belirlemek için bu yöntemi çağırın.|  
|[CPathT::IsSameRoot](#issameroot)|Başka bir yol geçerli yolda bir ortak kök bileşeni olup olmadığını belirlemek için bu yöntemi çağırın.|  
|[CPathT::IsUNC](#isunc)|Yolun bir sunucu için geçerli bir UNC (Evrensel Adlandırma Kuralı) yolu olup olmadığını belirlemek için bu yöntemi çağırın ve paylaşın.|  
|[CPathT::IsUNCServer](#isuncserver)|Yolun yalnızca bir sunucu için geçerli bir UNC (Evrensel Adlandırma Kuralı) yolu olup olmadığını belirlemek için bu yöntemi çağırın.|  
|[CPathT::IsUNCServerShare](#isuncservershare)|Yolun geçerli bir UNC (Evrensel Adlandırma Kuralı) paylaşım yolu olup olmadığını belirlemek için bu yöntemi çağırın \\ \  *server*\ *paylaşmak*.|  
|[CPathT::MakePretty](#makepretty)|Tutarlı bir görünüm yolunu vermek için küçük harfli karakterler için bir yol dönüştürmek için bu yöntemi çağırın.|  
|[CPathT::MatchSpec](#matchspec)|Yolun bir joker karakter eşleştirme türü içeren bir dize aramak için bu yöntemi çağırın.|  
|[CPathT::QuoteSpaces](#quotespaces)|Boşluk karakterleri içeriyorsa, yolu tırnak işaretleri içine alın için bu yöntemi çağırın.|  
|[CPathT::RelativePathTo](#relativepathto)|Bir dosya veya klasör başka bir göreli bir yol oluşturmak için bu yöntemi çağırın.|  
|[CPathT::RemoveArgs](#removeargs)|Herhangi bir komut satırı bağımsız değişkeni yolundan kaldırmak için bu yöntemi çağırın.|  
|[CPathT::RemoveBackslash](#removebackslash)|Eğik yolundan kaldırmak için bu yöntemi çağırın.|  
|[CPathT::RemoveBlanks](#removeblanks)|Tüm öndeki ve sondaki boşlukları yolundan kaldırmak için bu yöntemi çağırın.|  
|[CPathT::RemoveExtension](#removeextension)|Varsa yolundan dosya uzantısını kaldırmak için bu yöntemi çağırın.|  
|[CPathT::RemoveFileSpec](#removefilespec)|Bunları varsa sonunda dosya adı ve ters eğik çizgi yolundan kaldırmak için bu yöntemi çağırın.|  
|[CPathT::RenameExtension](#renameextension)|Yeni bir uzantıyla yolunda dosya adı uzantısı değiştirmek için bu yöntemi çağırın. Dosya adı uzantısı yoksa, uzantı dize sonuna eklenir.|  
|[CPathT::SkipRoot](#skiproot)|Sürücü harfi veya UNC paylaşımı/yol bölümü yok sayılıyor bir yolu ayrıştırmak için bu yöntemi çağırın.|  
|[CPathT::StripPath](#strippath)|Bir tam yol ve dosya adı yol kısmı kaldırmak için bu yöntemi çağırın.|  
|[CPathT::StripToRoot](#striptoroot)|Yolun kök bilgileri hariç tüm bölümlerini kaldırmak için bu yöntemi çağırın.|  
|[CPathT::UnquoteSpaces](#unquotespaces)|Başlangıç ve bitiş bir yolu tırnak işaretleri kaldırmak için bu yöntemi çağırın.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPathT::operator const StringType &](#operator_const_stringtype_amp)|Bu işleç gibi bir dizeyi kabul edilmesi nesne sağlar.|  
|[CPathT::operator CPathT::PCXSTR](#operator_cpatht__pcxstr)|Bu işleç gibi bir dizeyi kabul edilmesi nesne sağlar.|  
|[CPathT::operator StringType &](#operator_stringtype)|Bu işleç gibi bir dizeyi kabul edilmesi nesne sağlar.|  
|[CPathT::operator +=](#operator_add_eq)|Bu işleç yoluna bir dize ekler.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPathT::m_strPath](#m_strpath)|Yolu.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CPath`, `CPathA`, ve `CPathW` işlemlerinden olan `CPathT` tanımı aşağıdaki gibidir:  
  
 `typedef CPathT< CString > CPath;`  
  
 `typedef CPathT< CStringA > CPathA;`  
  
 `typedef CPathT< CStringW > CPathW;`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlpath.h  
  
##  <a name="addbackslash"></a>CPathT::AddBackslash  
 Eğik bir yolu doğru sözdizimi oluşturmak için bir dize sonu eklemek için bu yöntemi çağırın. Yolu bir eğik zaten varsa, ters eğik çizgi yok eklenir.  
  
```
void AddBackslash();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathAddBackSlash](http://msdn.microsoft.com/library/windows/desktop/bb773561).  
  
##  <a name="addextension"></a>CPathT::AddExtension  
 Bir dosya uzantısı için bir yol eklemek için bu yöntemi çağırın.  
  
```
BOOL AddExtension(PCXSTR pszExtension);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszExtension`  
 Eklemek için dosya uzantısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563).  
  
##  <a name="append"></a>CPathT::Append  
 Geçerli yolu bir dize eklemek için bu yöntemi çağırın.  
  
```
BOOL Append(PCXSTR pszMore);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszMore`  
 Eklenecek dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565).  
  
##  <a name="buildroot"></a>CPathT::BuildRoot  
 Belirtilen sürücü numarasından kök yolu oluşturmak için bu yöntemi çağırın.  
  
```
void BuildRoot(int iDrive);
```  
  
### <a name="parameters"></a>Parametreler  
 *iDrive*  
 Sürücü numarasını (0 A:, 1. B: vb.).  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567).  
  
##  <a name="canonicalize"></a>CPathT::Canonicalize  
 Kurallı biçimi yolu dönüştürmek için bu yöntemi çağırın.  
  
```
void Canonicalize();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569).  
  
##  <a name="combine"></a>CPathT::Combine  
 Bir dizin adı temsil eden bir dize ve bir dosya yolu adı tek bir yol temsil eden bir dize birleştirmek için bu yöntemi çağırın.  
  
```
void Combine(PCXSTR pszDir, PCXSTR  pszFile);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszDir`  
 Dizin yolu.  
  
 *pszFile*  
 Dosya yolu.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571).  
  
##  <a name="commonprefix"></a>CPathT::CommonPrefix  
 Belirtilen yol geçerli yoluna sahip ortak bir önek paylaşır olup olmadığını belirlemek için bu yöntemi çağırın.  
  
```
CPathT<StringType> CommonPrefix(PCXSTR pszOther);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszOther`  
 Geçerli bir Karşılaştırılacak yolu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ortak önek döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu tür bir önek biridir: "C:\\\\",".","..",".. \\\\". Daha fazla bilgi için bkz: [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574).  
  
##  <a name="compactpath"></a>CPathT::CompactPath  
 Üç nokta ile yol bileşenlerini değiştirerek içinde verilen piksel genişliği sığması için bir dosya yolu kesmek için bu yöntemi çağırın.  
  
```
BOOL CompactPath(HDC hDC, UINT nWidth);
```  
  
### <a name="parameters"></a>Parametreler  
 `hDC`  
 Yazı tipi ölçümleri için kullanılan cihaz bağlamı.  
  
 `nWidth`  
 Piksel cinsinden genişliği, dize sığmayacak zorlanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575).  
  
##  <a name="compactpathex"></a>CPathT::CompactPathEx  
 Üç nokta ile yol bileşenlerini değiştirerek belirli sayıda karakteri içinde sığması için bir dosya yolu kesmek için bu yöntemi çağırın.  
  
```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `nMaxChars`  
 Sondaki boş karakter dahil olmak üzere yeni dize içermesi gereken karakter sayısı.  
  
 `dwFlags`  
 Ayrılmış.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578).  
  
##  <a name="cpatht"></a>CPathT::CPathT  
 Oluşturucu.  
  
```
CPathT(PCXSTR pszPath);
CPathT(const CPathT<StringType>& path);
CPathT() throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *pszPath*  
 Yol dizesi yönelik işaretçi.  
  
 *yol*  
 Yol dizesi.  
  
##  <a name="fileexists"></a>CPathT::FileExists  
 Bu yol adı konumundaki dosya var olup olmadığını denetlemek için bu yöntemi çağırın.  
  
```
BOOL FileExists() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 DOĞRU dosya, yanlış Aksi durumda olup olmadığını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584).  
  
##  <a name="findextension"></a>CPathT::FindExtension  
 Dosya uzantısı yolu içindeki konumunu bulmak için bu yöntemi çağırın.  
  
```
int FindExtension() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Konumunu döndürür "." uzantısı önceki. Hiçbir uzantı bulunursa, -1 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587).  
  
##  <a name="findfilename"></a>CPathT::FindFileName  
 Yol dosya adını konumunu bulmak için bu yöntemi çağırın.  
  
```
int FindFileName() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dosya adı konumunu döndürür. Hiçbir dosya adı bulunursa, -1 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589).  
  
##  <a name="getdrivenumber"></a>CPathT::GetDriveNumber  
 'A'-'Z' aralığında bir sürücü harfi yolu arayın ve karşılık gelen sürücü sayı döndürmek için bu yöntemi çağırın.  
  
```
int GetDriveNumber() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yolun bir sürücü harfi veya -1 aksi varsa sürücü sayısı bir tamsayı olarak 0'dan 25 ('A'-'Z' karşılık gelen) döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612).  
  
##  <a name="getextension"></a>CPathT::GetExtension  
 Dosya uzantısı yolundan almak için bu yöntemi çağırın.  
  
```
StringType GetExtension() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dosya uzantısı döndürür.  
  
##  <a name="isdirectory"></a>CPathT::IsDirectory  
 Yolun geçerli bir dizin olup olmadığını denetlemek için bu yöntemi çağırın.  
  
```
BOOL IsDirectory() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yol bir dizin ise sıfır olmayan bir değer (16) döndürür `FALSE` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621).  
  
##  <a name="isfilespec"></a>CPathT::IsFileSpec  
 Yol sınırlandırma karakterler için bir yol aramak için bu yöntemi çağırın (örneğin, ':' veya '\\'). Mevcut hiçbir yolu ayıran karakter varsa, yol dosya Spec yolu olarak kabul edilir.  
  
```
BOOL IsFileSpec() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hiçbir yolu ayıran karakter yolu içindeki varsa TRUE veya FALSE yolu ayıran karakter varsa döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627).  
  
##  <a name="isprefix"></a>CPathT::IsPrefix  
 Bir yol geçirilen türü geçerli bir önek içerip içermediğini belirlemek için bu yöntemi çağırın `pszPrefix`.  
  
```
BOOL IsPrefix(PCXSTR pszPrefix) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `pszPrefix`  
 Aranacak önek. Bu tür bir önek biridir: "C:\\\\",".","..",".. \\\\".  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yol önek veya yanlış aksi içeriyorsa TRUE değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650).  
  
##  <a name="isrelative"></a>CPathT::IsRelative  
 Yolun göreli olup olmadığını belirlemek için bu yöntemi çağırın.  
  
```
BOOL IsRelative() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Mutlak yolu göreli ya da FALSE ise TRUE değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660).  
  
##  <a name="isroot"></a>CPathT::IsRoot  
 Yol bir dizin kök olup olmadığını belirlemek için bu yöntemi çağırın.  
  
```
BOOL IsRoot() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aksi halde bir kök veya yanlış yol olduğunda, TRUE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674).  
  
##  <a name="issameroot"></a>CPathT::IsSameRoot  
 Başka bir yol geçerli yolda bir ortak kök bileşeni olup olmadığını belirlemek için bu yöntemi çağırın.  
  
```
BOOL IsSameRoot(PCXSTR pszOther) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `pszOther`  
 Diğer bir yolu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her iki dize aynı kök bileşeni ya da FALSE aksi varsa TRUE değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687).  
  
##  <a name="isunc"></a>CPathT::IsUNC  
 Yolun bir sunucu için geçerli bir UNC (Evrensel Adlandırma Kuralı) yolu olup olmadığını belirlemek için bu yöntemi çağırın ve paylaşın.  
  
```
BOOL IsUNC() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yol geçerli bir UNC yolu veya yanlış Aksi durumda ise TRUE değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathIsUNC'yi](http://msdn.microsoft.com/library/windows/desktop/bb773712).  
  
##  <a name="isuncserver"></a>CPathT::IsUNCServer  
 Yolun yalnızca bir sunucu için geçerli bir UNC (Evrensel Adlandırma Kuralı) yolu olup olmadığını belirlemek için bu yöntemi çağırın.  
  
```
BOOL IsUNCServer() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 DOĞRU dizesi geçerli bir UNC yolu yalnızca bir sunucuya (paylaşım adı yok), veya yanlış değilse döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722).  
  
##  <a name="isuncservershare"></a>CPathT::IsUNCServerShare  
 Yolun geçerli bir UNC (Evrensel Adlandırma Kuralı) paylaşım yolu olup olmadığını belirlemek için bu yöntemi çağırın \\ \  *server*\ *paylaşmak*.  
  
```
BOOL IsUNCServerShare() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yol biçiminde ise TRUE verir \\ \  *server*\ *paylaşmak*, false Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723).  
  
##  <a name="m_strpath"></a>CPathT::m_strPath  
 Yolu.  
  
```
StringType m_strPath;
```  
  
### <a name="remarks"></a>Açıklamalar  
 `StringType`Şablon parametresi `CPathT`.  
  
##  <a name="makepretty"></a>CPathT::MakePretty  
 Tutarlı bir görünüm yolunu vermek için küçük harfli karakterler için bir yol dönüştürmek için bu yöntemi çağırın.  
  
```
BOOL MakePretty();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aksi takdirde, yolun dönüştürülürse TRUE veya FALSE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725).  
  
##  <a name="matchspec"></a>CPathT::MatchSpec  
 Yolun bir joker karakter eşleştirme türü içeren bir dize aramak için bu yöntemi çağırın.  
  
```
BOOL MatchSpec(PCXSTR pszSpec) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `pszSpec`  
 Aranacak dosya türü null ile sonlandırılmış bir dizeyle işaretçi. Örneğin, bir belge dosyası geçerli yolda dosya olup olmadığını sınamak için `pszSpec` ayarlanması gerekir "* .doc".  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aksi takdirde, dize eşleşmesi durumunda TRUE veya FALSE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727).  
  
##  <a name="operator_add_eq"></a>CPathT::operator +=  
 Bu işleç yoluna bir dize ekler.  
  
```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszMore`  
 Eklenecek dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş yolunu döndürür.  
  
##  <a name="operator_const_stringtype_amp"></a>CPathT::operator const StringType&amp;  
 Bu işleç gibi bir dizeyi kabul edilmesi nesne sağlar.  
  
```
 operatorconst StringType&() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu nesne tarafından yönetilen geçerli yolu temsil eden bir dize döndürür.  
  
##  <a name="operator_cpatht__pcxstr"></a>CPathT::operator CPathT::PCXSTR  
 Bu işleç gibi bir dizeyi kabul edilmesi nesne sağlar.  
  
```
 operatorPCXSTR() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu nesne tarafından yönetilen geçerli yolu temsil eden bir dize döndürür.  
  
##  <a name="operator_stringtype__amp"></a>CPathT::operator StringType&amp;  
 Bu işleç gibi bir dizeyi kabul edilmesi nesne sağlar.  
  
```
 operatorStringType&() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu nesne tarafından yönetilen geçerli yolu temsil eden bir dize döndürür.  
  
##  <a name="pcxstr"></a>CPathT::PCXSTR  
 Bir sabit dize türü.  
  
```
typedef StringType::PCXSTR PCXSTR;
```  
  
### <a name="remarks"></a>Açıklamalar  
 `StringType`Şablon parametresi `CPathT`.  
  
##  <a name="pxstr"></a>CPathT::PXSTR  
 Bir dize türü.  
  
```
typedef StringType::PXSTR PXSTR;
```  
  
### <a name="remarks"></a>Açıklamalar  
 `StringType`Şablon parametresi `CPathT`.  
  
##  <a name="quotespaces"></a>CPathT::QuoteSpaces  
 Boşluk karakterleri içeriyorsa, yolu tırnak işaretleri içine alın için bu yöntemi çağırın.  
  
```
void QuoteSpaces();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739).  
  
##  <a name="relativepathto"></a>CPathT::RelativePathTo  
 Bir dosya veya klasör başka bir göreli bir yol oluşturmak için bu yöntemi çağırın.  
  
```
BOOL RelativePathTo(
    PCXSTR pszFrom,
    DWORD dwAttrFrom,
    PCXSTR pszTo,
    DWORD dwAttrTo);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszFrom`  
 Göreli yolu başlangıcı.  
  
 *dwAttrFrom*  
 Dosya özniteliklerini `pszFrom`. Bu değer FILE_ATTRIBUTE_DIRECTORY, içeriyorsa `pszFrom` varsayılan bir dizin olmalıdır; aksi takdirde, `pszFrom` bir dosya olarak kabul edilir.  
  
 `pszTo`  
 Göreli yolu bitiş noktası.  
  
 *dwAttrTo*  
 Dosya özniteliklerini `pszTo`. Bu değer FILE_ATTRIBUTE_DIRECTORY, içeriyorsa `pszTo` varsayılan bir dizin olmalıdır; aksi takdirde, `pszTo` bir dosya olarak kabul edilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740).  
  
##  <a name="removeargs"></a>CPathT::RemoveArgs  
 Herhangi bir komut satırı bağımsız değişkeni yolundan kaldırmak için bu yöntemi çağırın.  
  
```
void RemoveArgs();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742).  
  
##  <a name="removebackslash"></a>CPathT::RemoveBackslash  
 Eğik yolundan kaldırmak için bu yöntemi çağırın.  
  
```
void RemoveBackslash();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743).  
  
##  <a name="removeblanks"></a>CPathT::RemoveBlanks  
 Tüm öndeki ve sondaki boşlukları yolundan kaldırmak için bu yöntemi çağırın.  
  
```
void RemoveBlanks();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745).  
  
##  <a name="removeextension"></a>CPathT::RemoveExtension  
 Varsa yolundan dosya uzantısını kaldırmak için bu yöntemi çağırın.  
  
```
void RemoveExtension();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746).  
  
##  <a name="removefilespec"></a>CPathT::RemoveFileSpec  
 Bunları varsa sonunda dosya adı ve ters eğik çizgi yolundan kaldırmak için bu yöntemi çağırın.  
  
```
BOOL RemoveFileSpec();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748).  
  
##  <a name="renameextension"></a>CPathT::RenameExtension  
 Yeni bir uzantıyla yolunda dosya adı uzantısı değiştirmek için bu yöntemi çağırın. Dosya adı uzantısı yoksa, uzantı yolunun sonuna eklenir.  
  
```
BOOL RenameExtension(PCXSTR pszExtension);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszExtension`  
 Yeni dosya adı uzantısı öncesinde tarafından bir "." karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749).  
  
##  <a name="skiproot"></a>CPathT::SkipRoot  
 Sürücü harfi veya UNC (Evrensel Adlandırma Kuralı) paylaşımı/yol bölümü yok sayılıyor bir yolu ayrıştırmak için bu yöntemi çağırın.  
  
```
int SkipRoot() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 (Sürücü harfi veya UNC paylaşımı /) kök izleyen alt başlangıcı konumunu döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754).  
  
##  <a name="strippath"></a>CPathT::StripPath  
 Bir tam yol ve dosya adı yol kısmı kaldırmak için bu yöntemi çağırın.  
  
```
void StripPath();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756).  
  
##  <a name="striptoroot"></a>CPathT::StripToRoot  
 Yolun kök bilgileri hariç tüm bölümlerini kaldırmak için bu yöntemi çağırın.  
  
```
BOOL StripToRoot();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir sürücü harfi, TRUE döndürür bulundu yolunda ya da yanlış Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757).  
  
##  <a name="unquotespaces"></a>CPathT::UnquoteSpaces  
 Başlangıç ve bitiş bir yolu tırnak işaretleri kaldırmak için bu yöntemi çağırın.  
  
```
void UnquoteSpaces();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763).  
  
##  <a name="xchar"></a>CPathT::XCHAR  
 Bir karakter türü.  
  
```
typedef StringType::XCHAR XCHAR;
```  
  
### <a name="remarks"></a>Açıklamalar  
 `StringType`Şablon parametresi `CPathT`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../atl/reference/atl-classes.md)   
 [CStringT sınıfı](../../atl-mfc-shared/reference/cstringt-class.md)