---
title: ATL Path fonksiyonları
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, path
f1_keywords:
- ATLPATH/ATL::ATLPath::AddBackslash
- ATLPATH/ATL::ATLPath::AddExtension
- ATLPATH/ATL::ATLPath::Append
- ATLPATH/ATL::ATLPath::BuildRoot
- ATLPATH/ATL::ATLPath::Canonicalize
- ATLPATH/ATL::ATLPath::Combine
- ATLPATH/ATL::ATLPath::CommonPrefix
- ATLPATH/ATL::ATLPath::CompactPath
- ATLPATH/ATL::ATLPath::CompactPathEx
- ATLPATH/ATL::ATLPath::FileExists
- ATLPATH/ATL::ATLPath::FindExtension
- ATLPATH/ATL::ATLPath::FindFileName
- ATLPATH/ATL::ATLPath::GetDriveNumber
- ATLPATH/ATL::ATLPath::IsDirectory
- ATLPATH/ATL::ATLPath::IsFileSpec
- ATLPATH/ATL::ATLPath::IsPrefix
- ATLPATH/ATL::ATLPath::IsRelative
- ATLPATH/ATL::ATLPath::IsRoot
- ATLPATH/ATL::ATLPath::IsSameRoot
- ATLPATH/ATL::ATLPath::IsUNC
- ATLPATH/ATL::ATLPath::IsUNCServer
- ATLPATH/ATL::ATLPath::IsUNCServerShare
- ATLPATH/ATL::ATLPath::MakePretty
- ATLPATH/ATL::ATLPath::MatchSpec
- ATLPATH/ATL::ATLPath::QuoteSpaces
- ATLPATH/ATL::ATLPath::RelativePathTo
- ATLPATH/ATL::ATLPath::RemoveArgs
- ATLPATH/ATL::ATLPath::RemoveBackslash
- ATLPATH/ATL::ATLPath::RemoveBlanks
- ATLPATH/ATL::ATLPath::RemoveExtension
- ATLPATH/ATL::ATLPath::RemoveFileSpec
- ATLPATH/ATL::ATLPath::RenameExtension
- ATLPATH/ATL::ATLPath::SkipRoot
- ATLPATH/ATL::ATLPath::StripPath
- ATLPATH/ATL::ATLPath::StripToRoot
- ATLPATH/ATL::ATLPath::UnquoteSpaces
ms.assetid: d1ec2b8d-7ec7-43ea-90dd-0a740d2a742b
ms.openlocfilehash: f3d8fa63e7fd20f8a0d6759fee8417b3fbc29486
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319214"
---
# <a name="atl-path-functions"></a>ATL Path fonksiyonları

ATL [CPathT](cpatht-class.md)şeklinde yolları işlemek için ATLPath sınıfını sağlar. Bu kod atlpath.h bulunabilir.

### <a name="related-classes"></a>İlgili Sınıflar

|||
|-|-|
|[CPathT Sınıfı](cpatht-class.md)|Bu sınıf bir yolu temsil eder.|

### <a name="related-typedefs"></a>İlgili Typedefs

|||
|-|-|
|`CPath`|[CPathT'nin](cpatht-class.md) uzmanlık `CString`alanı .|
|`CPathA`|[CPathT'nin](cpatht-class.md) uzmanlık `CStringA`alanı .|
|`CPathW`|[CPathT'nin](cpatht-class.md) uzmanlık `CStringW`alanı .|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[ATLPath::AddBackslash](#addbackslash)|Bu işlev [PathAddBackslash](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::AddExtension](#addextension)|Bu işlev [PathAddExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::Ek](#append)|Bu işlev [PathAppend](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)için aşırı yüklenmiş bir sarıcıdır.|
|[ATLPath::BuildRoot](#buildroot)|Bu işlev [PathBuildRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::Canonicalize](#canonicalize)|Bu fonksiyon [PathCanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::Birleştir](#combine)|Bu işlev [PathCombine](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::CommonPrefix](#commonprefix)|Bu işlev [PathCommonPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::CompactPath](#compactpath)|Bu işlev [PathCompactPath](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::CompactPathEx](#compactpathex)|Bu fonksiyon [PathCompactPathEx](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)için aşırı yüklenmiş bir sarıcıdır.|
|[ATLPath::FileExists](#fileexists)|Bu işlev [PathFileExists](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::FindExtension](#findextension)|Bu işlev [PathFindExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)için aşırı yüklü bir sarmalayıcıdır.|
|[ATLPath::FindFileName](#findfilename)|Bu işlev [PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath::GetDriveNumber](#getdrivenumber)|Bu işlev [PathGetDriveNumber](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::İş Dizini](#isdirectory)|Bu işlev [PathIsDirectory](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::IsFileSpec](#isfilespec)|Bu işlev [PathIsFileSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)için aşırı yüklenmiş bir sarıcıdır.|
|[ATLPath::Düzeltme](#isprefix)|Bu işlev [PathIsPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::Göreli](#isrelative)|Bu işlev [PathIsRelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::Isroot](#isroot)|Bu fonksiyon [PathIsRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)için aşırı yüklenmiş bir sarıcıdır.|
|[ATLPath::Issameroot](#issameroot)|Bu fonksiyon [PathIsSameRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw)için aşırı yüklenmiş bir sarıcıdır.|
|[ATLPath::IsUNC](#isunc)|Bu işlev [PathIsUNC](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)için aşırı yüklenmiş bir sarıcıdır.|
|[ATLPath::IsUNCServer](#isuncserver)|Bu işlev [PathIsUNCServer](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw)için aşırı yüklenmiş bir sarıcıdır.|
|[ATLPath::IsUNCServerShare](#isuncservershare)|Bu işlev [PathIsUNCServerShare](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::MakePretty](#makepretty)|Bu fonksiyon [PathMakePretty](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::MatchSpec](#matchspec)|Bu işlev [PathMatchSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::Alıntı Alanları](#quotespaces)|Bu işlev [PathQuoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::RelativePathTo](#relativepathto)|Bu işlev [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::RemoveArgs](#removeargs)|Bu işlev [PathRemoveArgs](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::RemoveBackslash](#removebackslash)|Bu işlev [PathRemoveBackslash](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::Boşlukları Kaldır](#removeblanks)|Bu işlev [PathRemoveBlanks](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::RemoveExtension](#removeextension)|Bu işlev [PathRemoveExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::RemoveFileSpec](#removefilespec)|Bu işlev [PathRemoveFileSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)için aşırı yüklü bir sarmalayıcıdır.|
|[ATLPath::RenameExtension](#renameextension)|Bu işlev [PathRenameExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::SkipRoot](#skiproot)|Bu işlev [PathSkipRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::StripPath](#strippath)|Bu işlev [PathStripPath](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::Striptoroot](#striptoroot)|Bu işlev [PathStripToRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)için aşırı yüklü bir sarıcıdır.|
|[ATLPath::Alıntı Sızma Alanları](#unquotespaces)|Bu işlev [PathUnquoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)için aşırı yüklü bir sarıcıdır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlpath.h

## <a name="atlpathaddbackslash"></a><a name="addbackslash"></a>ATLPath::AddBackSlash

Bu işlev [PathAddBackslash](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline char* AddBackslash(char* pszPath);
inline wchar_t* AddBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathAddBackslash'e](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw) bakın.

## <a name="atlpathaddextension"></a><a name="addextension"></a>ATLPath::AddExtension

Bu işlev [PathAddExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline BOOL AddExtension(char* pszPath, const char* pszExtension);
inline BOOL AddExtension(wchar_t* pszPath, const wchar_t* pszExtension);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathAddExtension'a](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw) bakın.

## <a name="atlpathappend"></a><a name="append"></a>ATLPath::Ek

Bu işlev [PathAppend](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)için aşırı yüklenmiş bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline BOOL Append(char* pszPath, const char* pszMore);
inline BOOL Append(wchar_t* pszPath, const wchar_t* pszMore);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathAppend'e](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw) bakın.

## <a name="atlpathbuildroot"></a><a name="buildroot"></a>ATLPath::BuildRoot

Bu işlev [PathBuildRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline char* BuildRoot(char* pszPath, int iDrive);
inline wchar_t* BuildRoot(wchar_t* pszPath, int iDrive);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathBuildRoot'a](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw) bakın.

## <a name="atlpathcanonicalize"></a><a name="canonicalize"></a>ATLPath::Canonicalize

Bu fonksiyon [PathCanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline BOOL Canonicalize(char* pszDest, const char* pszSrc);
inline BOOL Canonicalize(wchar_t* pszDest, const wchar_t* pszSrc);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathCanonicalize'ye](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew) bakın.

## <a name="atlpathcombine"></a><a name="combine"></a>ATLPath::Birleştir

Bu işlev [PathCombine](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew)için aşırı yüklü bir sarıcıdır.

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

Ayrıntılar için PathCombine'a bakın.

## <a name="atlpathcommonprefix"></a><a name="commonprefix"></a>ATLPath::CommonPrefix

Bu işlev [PathCommonPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)için aşırı yüklü bir sarıcıdır.

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

Ayrıntılar için [PathCommonPrefix'e](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw) bakın.

## <a name="atlpathcompactpath"></a><a name="compactpath"></a>ATLPath::CompactPath

Bu işlev [PathCompactPath](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)için aşırı yüklü bir sarıcıdır.

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

Ayrıntılar için [PathCompactPath'e](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw) bakın.

## <a name="atlpathcompactpathex"></a><a name="compactpathex"></a>ATLPath::CompactPathEx

Bu fonksiyon [PathCompactPathEx](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)için aşırı yüklenmiş bir sarıcıdır.

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

Ayrıntılar için [PathCompactPathEx'e](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw) bakın.

## <a name="atlpathfileexists"></a><a name="fileexists"></a>ATLPath::FileExists

Bu işlev [PathFileExists](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline BOOL FileExists(const char* pszPath);
inline BOOL FileExists(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathFileExists'e](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw) bakın.

## <a name="atlpathfindextension"></a><a name="findextension"></a>ATLPath::FindExtension

Bu işlev [PathFindExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)için aşırı yüklü bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline char* FindExtension(const char* pszPath);
inline wchar_t* FindExtension(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathFindExtension'a](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw) bakın.

## <a name="atlpathfindfilename"></a><a name="findfilename"></a>ATLPath::FindFileName

Bu işlev [PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline char* FindFileName(const char* pszPath);
inline wchar_t* FindFileName(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathFindFileName'ye](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew) bakın.

## <a name="atlpathgetdrivenumber"></a><a name="getdrivenumber"></a>ATLPath::GetDriveNumber

Bu işlev [PathGetDriveNumber](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline int GetDriveNumber(const char* pszPath);
inline int GetDriveNumber(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathGetDriveNumber'a](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw) bakın.

## <a name="atlpathisdirectory"></a><a name="isdirectory"></a>ATLPath::İş Dizini

Bu işlev [PathIsDirectory](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw)için aşırı yüklü bir sarıcıdır.

```
inline BOOL IsDirectory(const char* pszPath);
inline BOOL IsDirectory(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için PathIsDirectory'ye bakın.

## <a name="atlpathisfilespec"></a><a name="isfilespec"></a>ATLPath::IsFileSpec

Bu işlev [PathIsFileSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)için aşırı yüklenmiş bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline BOOL IsFileSpec(const char* pszPath);
inline BOOL IsFileSpec(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathIsFileSpec'e](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw) bakın.

## <a name="atlpathisprefix"></a><a name="isprefix"></a>ATLPath::Düzeltme

Bu işlev [PathIsPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline BOOL IsPrefix(const char* pszPrefix, const char* pszPath);
inline BOOL IsPrefix(const wchar_t* pszPrefix, const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathIsPrefix'e](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw) bakın.

## <a name="atlpathisrelative"></a><a name="isrelative"></a>ATLPath::Göreli

Bu işlev [PathIsRelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline BOOL IsRelative(const char* pszPath);
inline BOOL IsRelative(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathIsRelative'a](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew) bakın.

## <a name="atlpathisroot"></a><a name="isroot"></a>ATLPath::Isroot

Bu fonksiyon [PathIsRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)için aşırı yüklenmiş bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline BOOL IsRoot(const char* pszPath);
inline BOOL IsRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathIsRoot'a](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw) bakın.

## <a name="atlpathissameroot"></a><a name="issameroot"></a>ATLPath::Issameroot

Bu fonksiyon [PathIsSameRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw)için aşırı yüklenmiş bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline BOOL IsSameRoot(const char* pszPath1, const char* pszPath2);
inline BOOL IsSameRoot(const wchar_t* pszPath1, const wchar_t* pszPath2);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathIsSameRoot'a](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw) bakın.

## <a name="atlpathisunc"></a><a name="isunc"></a>ATLPath::IsUNC

Bu işlev [PathIsUNC](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)için aşırı yüklenmiş bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline BOOL IsUNC(const char* pszPath);
inline BOOL IsUNC(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathIsUNC'a](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw) bakın.

## <a name="atlpathisuncserver"></a><a name="isuncserver"></a>ATLPath::IsUNCServer

Bu işlev [PathIsUNCServer](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw)için aşırı yüklenmiş bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline BOOL IsUNCServer(const char* pszPath);
inline BOOL IsUNCServer(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathIsUNCServer'a](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw) bakın.

## <a name="atlpathisuncservershare"></a><a name="isuncservershare"></a>ATLPath::IsUNCServerShare

Bu işlev [PathIsUNCServerShare](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline BOOL IsUNCServerShare(const char* pszPath);
inline BOOL IsUNCServerShare(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathIsUNCServerShare](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew) adresine bakın.

## <a name="atlpathmakepretty"></a><a name="makepretty"></a>ATLPath::MakePretty

Bu fonksiyon [PathMakePretty](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline BOOL MakePretty(char* pszPath);
inline BOOL MakePretty(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathMakePretty'ye](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw) bakın.

## <a name="atlpathmatchspec"></a><a name="matchspec"></a>ATLPath::MatchSpec

Bu işlev [PathMatchSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline BOOL MatchSpec(const char* pszPath, const char* pszSpec);
inline BOOL MatchSpec(const wchar_t* pszPath, const wchar_t* pszSpec);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathMatchSpec'e](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw) bakın.

## <a name="atlpathquotespaces"></a><a name="quotespaces"></a>ATLPath::Alıntı Alanları

Bu işlev [PathQuoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline void QuoteSpaces(char* pszPath);
inline void QuoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathQuoteSpaces'e](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw) bakın.

## <a name="atlpathrelativepathto"></a><a name="relativepathto"></a>ATLPath::RelativePathTo

Bu işlev [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow)için aşırı yüklü bir sarıcıdır.

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

Ayrıntılar için [PathRelativePathTo'ya](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow) bakın.

## <a name="atlpathremoveargs"></a><a name="removeargs"></a>ATLPath::RemoveArgs

Bu işlev [PathRemoveArgs](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline void RemoveArgs(char* pszPath);
inline void RemoveArgs(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathRemoveArgs'a](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw) bakın.

## <a name="atlpathremovebackslash"></a><a name="removebackslash"></a>ATLPath::RemoveBackslash

Bu işlev [PathRemoveBackslash](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline char* RemoveBackslash(char* pszPath);
inline wchar_t* RemoveBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathRemoveBackslash'e](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw) bakın.

## <a name="atlpathremoveblanks"></a><a name="removeblanks"></a>ATLPath::Boşlukları Kaldır

Bu işlev [PathRemoveBlanks](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline void RemoveBlanks(char* pszPath);
inline void RemoveBlanks(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathRemoveBlanks'a](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw) bakın.

## <a name="atlpathremoveextension"></a><a name="removeextension"></a>ATLPath::RemoveExtension

Bu işlev [PathRemoveExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline void RemoveExtension(char* pszPath);
inline void RemoveExtension(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathRemoveExtension'a](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw) bakın.

## <a name="atlpathremovefilespec"></a><a name="removefilespec"></a>ATLPath::RemoveFileSpec

Bu işlev [PathRemoveFileSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)için aşırı yüklü bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline BOOL RemoveFileSpec(char* pszPath);
inline BOOL RemoveFileSpec(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathRemoveFileSpec'e](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw) bakın.

## <a name="atlpathrenameextension"></a><a name="renameextension"></a>ATLPath::RenameExtension

Bu işlev [PathRenameExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline BOOL RenameExtension(char* pszPath, const char* pszExt);
inline BOOL RenameExtension(wchar_t* pszPath, const wchar_t* pszExt);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathRenameExtension'a](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw) bakın.

## <a name="atlpathskiproot"></a><a name="skiproot"></a>ATLPath::SkipRoot

Bu işlev [PathSkipRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline char* SkipRoot(const char* pszPath);
inline wchar_t* SkipRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathSkipRoot'a](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw) bakın.

## <a name="atlpathstrippath"></a><a name="strippath"></a>ATLPath::StripPath

Bu işlev [PathStripPath](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline void StripPath(char* pszPath);
inline void StripPath(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathStripPath'e](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw) bakın.

## <a name="atlpathstriptoroot"></a><a name="striptoroot"></a>ATLPath::Striptoroot

Bu işlev [PathStripToRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline BOOL StripToRoot(char* pszPath);
inline BOOL StripToRoot(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathStripToRoot'a](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw) bakın.

## <a name="atlpathunquotespaces"></a><a name="unquotespaces"></a>ATLPath::Alıntı Sızma Alanları

Bu işlev [PathUnquoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)için aşırı yüklü bir sarıcıdır.

### <a name="syntax"></a>Sözdizimi

```
inline void UnquoteSpaces(char* pszPath);
inline void UnquoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [PathUnquoteSpaces'e](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw) bakın.
