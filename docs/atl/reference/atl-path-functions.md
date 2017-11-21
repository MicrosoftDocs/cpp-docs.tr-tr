---
title: "ATL yolu işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
keywords: ATL, yol
ms.assetid: d1ec2b8d-7ec7-43ea-90dd-0a740d2a742b
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 97d585eb8bbe59a8ccd92b866819fb869d35f64c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="atl-path-functions"></a>ATL yolu işlevleri

ATL yolları biçiminde yönlendirmek için ATLPath sınıfı sağlar [CPathT](cpatht-class.md). Bu kod atlpath.h içinde bulunabilir.  
  
### <a name="related-classes"></a>İlgili sınıflar  
  
|||  
|-|-|  
|[CPathT sınıfı](cpatht-class.md)|Bu sınıf bir yolunu temsil eder.|  

### <a name="related-typedefs"></a>İlgili tür tanımları  
  
|||  
|-|-|  
|`CPath`|Bir alt uzmanlaşması [CPathT](cpatht-class.md) kullanarak `CString`.|  
|`CPathA`|Bir alt uzmanlaşması [CPathT](cpatht-class.md) kullanarak `CStringA`.|  
|`CPathW`|Bir alt uzmanlaşması [CPathT](cpatht-class.md) kullanarak `CStringW`.|  
  
### <a name="functions"></a>İşlevler  
  
|||  
|-|-|  
|[ATLPath::AddBackslash](#addbackslash)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561).|  
|[ATLPath::AddExtension](#addextension)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563).|  
|[ATLPath::Append](#append)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565).|  
|[ATLPath::BuildRoot](#buildroot)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567).|  
|[ATLPath::Canonicalize](#canonicalize)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569).|  
|[ATLPath::Combine](#combine)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571).|  
|[ATLPath::CommonPrefix](#commonprefix)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574).|  
|[ATLPath::CompactPath](#compactpath)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575).|  
|[ATLPath::CompactPathEx](#compactpathex)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578).|  
|[ATLPath::FileExists](#fileexists)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584).|  
|[ATLPath::FindExtension](#findextension)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587).|  
|[ATLPath::FindFileName](#findfilename)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589).|  
|[ATLPath::GetDriveNumber](#getdrivenumber)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612).|  
|[ATLPath::IsDirectory](#isdirectory)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621).|  
|[ATLPath::IsFileSpec](#isfilespec)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627).|  
|[ATLPath::IsPrefix](#isprefix)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650).|  
|[ATLPath::IsRelative](#isrelative)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660).|  
|[ATLPath::IsRoot](#isroot)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674).|  
|[ATLPath::IsSameRoot](#issameroot)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687).|  
|[ATLPath::IsUNC](#isunc)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsUNC'yi](http://msdn.microsoft.com/library/windows/desktop/bb773712).|  
|[ATLPath::IsUNCServer](#isuncserver)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722).|  
|[ATLPath::IsUNCServerShare](#isuncservershare)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723).|  
|[ATLPath::MakePretty](#makepretty)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725).|  
|[ATLPath::MatchSpec](#matchspec)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727).|  
|[ATLPath::QuoteSpaces](#quotespaces)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739).|  
|[ATLPath::RelativePathTo](#relativepathto)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740).|  
|[ATLPath::RemoveArgs](#removeargs)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742).|  
|[ATLPath::RemoveBackslash](#removebackslash)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743).|  
|[ATLPath::RemoveBlanks](#removeblanks)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745).|  
|[ATLPath::RemoveExtension](#removeextension)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746).|  
|[ATLPath::RemoveFileSpec](#removefilespec)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748).|  
|[ATLPath::RenameExtension](#renameextension)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749).|  
|[ATLPath::SkipRoot](#skiproot)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754).|  
|[ATLPath::StripPath](#strippath)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756).|  
|[ATLPath::StripToRoot](#striptoroot)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757).|  
|[ATLPath::UnquoteSpaces](#unquotespaces)|Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763).|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlpath.h  

## <a name="addbackslash"></a>ATLPath::AddBackSlash

Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline char* AddBackslash(char* pszPath);  
inline wchar_t* AddBackslash(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561) Ayrıntılar için.  
  
 
  

## <a name="addextension"></a>ATLPath::AddExtension
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL AddExtension(char* pszPath, const char* pszExtension);  
inline BOOL AddExtension(wchar_t* pszPath, const wchar_t* pszExtension);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563) Ayrıntılar için. 
  
## <a name="append"></a>ATLPath::Append
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL Append(char* pszPath, const char* pszMore);  
inline BOOL Append(wchar_t* pszPath, const wchar_t* pszMore);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565) Ayrıntılar için.  
  
 
  

## <a name="buildroot"></a>ATLPath::BuildRoot
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline char* BuildRoot(char* pszPath, int iDrive);  
inline wchar_t* BuildRoot(wchar_t* pszPath, int iDrive);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567) Ayrıntılar için.  
  
 
  

## <a name="canonicalize"></a>ATLPath::Canonicalize
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL Canonicalize(char* pszDest, const char* pszSrc);  
inline BOOL Canonicalize(wchar_t* pszDest, const wchar_t* pszSrc);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569) Ayrıntılar için.  
  
 
  

## <a name="combine"></a>ATLPath::Combine 
Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathCombine](https://msdn.microsoft.com/en-us/library/windows/desktop/bb773571).  

### <a name="syntax"></a>Sözdizimi  
```
inline char* Combine(  
   char* pszDest,
   const char* pszDir,
   const char* pszFile 
);

inline wchar_t* Combine(  
   wchar_t* pszDest,
   const wchar_t* pszDir,
   const wchar_t* pszFile);
```
### <a name="remarks"></a>Açıklamalar
PathCombine Ayrıntılar için bkz.


## <a name="commonprefix"></a>ATLPath::CommonPrefix
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline int CommonPrefix(  
   const char* pszFile1, 
   const char* pszFile2,  
   char* pszDest);  

inline int CommonPrefix(  
   const wchar_t* pszFile1,  
   const wchar_t* pszFile2,  
   wchar_t* pszDest);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574) Ayrıntılar için.  
  
 
  

## <a name="compactpath"></a>ATLPath::CompactPath
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL CompactPath(  
   HDC hDC,  
   char* pszPath,  
   UINT dx);  

inline BOOL CompactPath(  
   HDC hDC,  
   wchar_t* pszPath,  
   UINT dx);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575) Ayrıntılar için.  
  
 
  

## <a name="compactpathex"></a>ATLPath::CompactPathEx
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL CompactPathEx(  
   char* pszDest,  
   const char* pszSrc,  
   UINT nMaxChars,  
   DWORD dwFlags);  

inline BOOL CompactPathEx(  
   wchar_t* pszDest,  
   const wchar_t* pszSrc,  
   UINT nMaxChars,  
   DWORD dwFlags);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578) Ayrıntılar için.  
  
 
  

## <a name="fileexists"></a>ATLPath::FileExists
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL FileExists(const char* pszPath);  
inline BOOL FileExists(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584) Ayrıntılar için.  
  
 
  

## <a name="findextension"></a>ATLPath::FindExtension
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline char* FindExtension(const char* pszPath);  
inline wchar_t* FindExtension(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587) Ayrıntılar için.  
  
 
  

## <a name="findfilename"></a>ATLPath::FindFileName
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline char* FindFileName(const char* pszPath);  
inline wchar_t* FindFileName(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589) Ayrıntılar için.  
  
 
  

## <a name="getdrivenumber"></a>ATLPath::GetDriveNumber  
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline int GetDriveNumber(const char* pszPath);  
inline int GetDriveNumber(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612) Ayrıntılar için.  
  
 


## <a name="isdirectory"></a>ATLPath::IsDirectory 
Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsDirectory](https://msdn.microsoft.com/en-us/library/windows/desktop/bb773621).

```  
inline BOOL IsDirectory(const char* pszPath);
inline BOOL IsDirectory(const wchar_t* pszPath);
```  
### <a name="remarks"></a>Açıklamalar
PathIsDirectory Ayrıntılar için bkz.  

## <a name="isfilespec"></a>ATLPath::IsFileSpec
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL IsFileSpec(const char* pszPath);  
inline BOOL IsFileSpec(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627) Ayrıntılar için.  
  
 
  

## <a name="isprefix"></a>ATLPath::IsPrefix
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL IsPrefix(const char* pszPrefix, const char* pszPath);  
inline BOOL IsPrefix(const wchar_t* pszPrefix, const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650) Ayrıntılar için.  
  
 
  

## <a name="isrelative"></a>ATLPath::IsRelative
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL IsRelative(const char* pszPath);  
inline BOOL IsRelative(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660) Ayrıntılar için.  
  
 
  

## <a name="isroot"></a>ATLPath::IsRoot
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL IsRoot(const char* pszPath);  
inline BOOL IsRoot(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674) Ayrıntılar için.  
  
 
  

## <a name="issameroot"></a>ATLPath::IsSameRoot
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL IsSameRoot(const char* pszPath1, const char* pszPath2);  
inline BOOL IsSameRoot(const wchar_t* pszPath1, const wchar_t* pszPath2);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687) Ayrıntılar için.  
  
 
  

## <a name="isunc"></a>ATLPath::IsUNC
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsUNC'yi](http://msdn.microsoft.com/library/windows/desktop/bb773712).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL IsUNC(const char* pszPath);  
inline BOOL IsUNC(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathIsUNC'yi](http://msdn.microsoft.com/library/windows/desktop/bb773712) Ayrıntılar için.  
  
 
  

## <a name="isuncserver"></a>ATLPath::IsUNCServer
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL IsUNCServer(const char* pszPath);  
inline BOOL IsUNCServer(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722) Ayrıntılar için.  
  
 
  

## <a name="isuncservershare"></a>ATLPath::IsUNCServerShare
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL IsUNCServerShare(const char* pszPath);  
inline BOOL IsUNCServerShare(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723) Ayrıntılar için.  
  
 
  

## <a name="makepretty"></a>ATLPath::MakePretty
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL MakePretty(char* pszPath);  
inline BOOL MakePretty(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725) Ayrıntılar için.  
  
 
  

## <a name="matchspec"></a>ATLPath::MatchSpec  
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL MatchSpec(const char* pszPath, const char* pszSpec);  
inline BOOL MatchSpec(const wchar_t* pszPath, const wchar_t* pszSpec);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727) Ayrıntılar için.  
  
 
  

## <a name="quotespaces"></a>ATLPath::QuoteSpaces  
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline void QuoteSpaces(char* pszPath);  
inline void QuoteSpaces(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739) Ayrıntılar için.  
  
 
  

## <a name="relativepathto"></a>ATLPath::RelativePathTo
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL RelativePathTo(  
   char* pszPath,  
   const char* pszFrom,  
   DWORD dwAttrFrom,  
   const char* pszTo,  
   DWORD dwAttrTo);  

inline BOOL RelativePathTo(  
   wchar_t* pszPath,  
   const wchar_t* pszFrom,  
   DWORD dwAttrFrom,  
   const wchar_t* pszTo,  
   DWORD dwAttrTo);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740) Ayrıntılar için.  
  
 
  

## <a name="removeargs"></a>ATLPath::RemoveArgs  
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline void RemoveArgs(char* pszPath);  
inline void RemoveArgs(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742) Ayrıntılar için.  
  
 
  

## <a name="removebackslash"></a>ATLPath::RemoveBackslash
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline char* RemoveBackslash(char* pszPath);  
inline wchar_t* RemoveBackslash(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743) Ayrıntılar için.  
  
 
  

## <a name="removeblanks"></a>ATLPath::RemoveBlanks
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline void RemoveBlanks(char* pszPath);  
inline void RemoveBlanks(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745) Ayrıntılar için.  
  
 
  

## <a name="removeextension"></a>ATLPath::RemoveExtension
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline void RemoveExtension(char* pszPath);  
inline void RemoveExtension(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746) Ayrıntılar için.  
  
 
  

## <a name="removefilespec"></a>ATLPath::RemoveFileSpec
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL RemoveFileSpec(char* pszPath);  
inline BOOL RemoveFileSpec(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748) Ayrıntılar için.  
  
 
  

## <a name="renameextension"></a>ATLPath::RenameExtension
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL RenameExtension(char* pszPath, const char* pszExt);  
inline BOOL RenameExtension(wchar_t* pszPath, const wchar_t* pszExt);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749) Ayrıntılar için.  
  
 
  

## <a name="skiproot"></a>ATLPath::SkipRoot
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline char* SkipRoot(const char* pszPath);  
inline wchar_t* SkipRoot(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754) Ayrıntılar için.  
  
 
  

## <a name="strippath"></a>ATLPath::StripPath
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline void StripPath(char* pszPath);  
inline void StripPath(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756) Ayrıntılar için.  
  
 
  


## <a name="striptoroot"></a>ATLPath::StripToRoot
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline BOOL StripToRoot(char* pszPath);  
inline BOOL StripToRoot(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757) Ayrıntılar için.  
  
 
  

## <a name="unquotespaces"></a>ATLPath::UnquoteSpaces
 Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
inline void UnquoteSpaces(char* pszPath);  
inline void UnquoteSpaces(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763) Ayrıntılar için.  
  
 
  
 
