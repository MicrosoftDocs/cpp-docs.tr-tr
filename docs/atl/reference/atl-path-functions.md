---
title: ATL yol işlevleri
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
ms.openlocfilehash: 2ab8dfc2e9d5789b7ee67f8082f28cf228608663
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168805"
---
# <a name="atl-path-functions"></a>ATL yol işlevleri

ATL, [CPathT](cpatht-class.md)biçimindeki yolları Işlemek Için ATLPath sınıfını sağlar. Bu kod, atlpath. h içinde bulunabilir.

## <a name="related-classes"></a>İlgili sınıflar

|||
|-|-|
|[CPathT Sınıfı](cpatht-class.md)|Bu sınıf bir yolu temsil eder.|

## <a name="related-typedefs"></a>İlgili tür tanımları

|||
|-|-|
|`CPath`|Kullanarak `CString` [CPathT](cpatht-class.md) özelleştirmesi.|
|`CPathA`|Kullanarak `CStringA` [CPathT](cpatht-class.md) özelleştirmesi.|
|`CPathW`|Kullanarak `CStringW` [CPathT](cpatht-class.md) özelleştirmesi.|

## <a name="functions"></a>İşlevler

|||
|-|-|
|[ATLPath:: Addters eğik çizgi](#addbackslash)|Bu işlev [Pathaddters eğik çizgi](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: Addexgeri](#addextension)|Bu işlev [Pathaddexgeri](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: Append](#append)|Bu işlev, [PathAppend](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: BuildRoot](#buildroot)|Bu işlev, [PathBuildRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: canonicalize](#canonicalize)|Bu işlev, [PathCanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: birleştirin](#combine)|Bu işlev, [Pathbirleştirme](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: CommonPrefix](#commonprefix)|Bu işlev, [PathCommonPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: CompactPath](#compactpath)|Bu işlev, [PathCompactPath](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: CompactPathEx](#compactpathex)|Bu işlev, [PathCompactPathEx](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: FileExists](#fileexists)|Bu işlev, [PathFileExists](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: Findexgeri](#findextension)|Bu işlev, [Pathfindexgeri](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: FindFileName](#findfilename)|Bu işlev, [PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: GetDriveNumber](#getdrivenumber)|Bu işlev, [PathGetDriveNumber](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: IsDirectory](#isdirectory)|Bu işlev [Pathisdirectory](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: ısdosyabelirtimi](#isfilespec)|Bu işlev [Pathisdosyabelirtimi](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: Isprefıx](#isprefix)|Bu işlev [Pathisprefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: ısgöreli](#isrelative)|Bu işlev, [Pathısgöreli](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: IsRoot](#isroot)|Bu işlev, [Pathisroot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: IsSameRoot](#issameroot)|Bu işlev [Pathissameroot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: IsUnc](#isunc)|Bu işlev [Pathisunc](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: ısuncserver](#isuncserver)|Bu işlev [Pathisuncserver](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: ısuncservershare](#isuncservershare)|Bu işlev [Pathisuncservershare](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: Makeoldukça](#makepretty)|Bu işlev, [Pathmakeoldukça](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: MatchSpec](#matchspec)|Bu işlev, [PathMatchSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: QuoteSpaces](#quotespaces)|Bu işlev, [PathQuoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: RelativePathTo](#relativepathto)|Bu işlev [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: RemoveArgs](#removeargs)|Bu işlev [PathRemoveArgs](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: Removeters eğik çizgi](#removebackslash)|Bu işlev [Pathremoveters eğik çizgi](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: Removeboşlar](#removeblanks)|Bu işlev, [Pathremoveboşluklar](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: RemoveExtension](#removeextension)|Bu işlev [PathRemoveExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: Removedosyabelirtimi](#removefilespec)|Bu işlev, [Pathremovedosyabelirtimi](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: RenameExtension](#renameextension)|Bu işlev [PathRenameExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: SkipRoot](#skiproot)|Bu işlev [PathSkipRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: StripPath](#strippath)|Bu işlev, [PathStripPath](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: StripToRoot](#striptoroot)|Bu işlev, [PathStripToRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)için aşırı yüklenmiş bir sarmalayıcıdır.|
|[ATLPath:: UnquoteSpaces](#unquotespaces)|Bu işlev, [PathUnquoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)için aşırı yüklenmiş bir sarmalayıcıdır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlpath. h

## <a name="atlpathaddbackslash"></a><a name="addbackslash"></a>ATLPath:: Addters eğik çizgi

Bu işlev [Pathaddters eğik çizgi](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline char* AddBackslash(char* pszPath);
inline wchar_t* AddBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [Pathaddters eğik çizgi](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw) .

## <a name="atlpathaddextension"></a><a name="addextension"></a>ATLPath:: Addexgeri

Bu işlev [Pathaddexgeri](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline BOOL AddExtension(char* pszPath, const char* pszExtension);
inline BOOL AddExtension(wchar_t* pszPath, const wchar_t* pszExtension);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [Pathaddexgeri](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw) .

## <a name="atlpathappend"></a><a name="append"></a>ATLPath:: Append

Bu işlev, [PathAppend](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline BOOL Append(char* pszPath, const char* pszMore);
inline BOOL Append(wchar_t* pszPath, const wchar_t* pszMore);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [PathAppend](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw) .

## <a name="atlpathbuildroot"></a><a name="buildroot"></a>ATLPath:: BuildRoot

Bu işlev, [PathBuildRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline char* BuildRoot(char* pszPath, int iDrive);
inline wchar_t* BuildRoot(wchar_t* pszPath, int iDrive);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [PathBuildRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw) .

## <a name="atlpathcanonicalize"></a><a name="canonicalize"></a>ATLPath:: canonicalize

Bu işlev, [PathCanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline BOOL Canonicalize(char* pszDest, const char* pszSrc);
inline BOOL Canonicalize(wchar_t* pszDest, const wchar_t* pszSrc);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [PathCanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew) .

## <a name="atlpathcombine"></a><a name="combine"></a>ATLPath:: birleştirin

Bu işlev, [Pathbirleştirme](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
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

Ayrıntılar için bkz. Pathbirleştirme.

## <a name="atlpathcommonprefix"></a><a name="commonprefix"></a>ATLPath:: CommonPrefix

Bu işlev, [PathCommonPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
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

Ayrıntılar için bkz. [PathCommonPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw) .

## <a name="atlpathcompactpath"></a><a name="compactpath"></a>ATLPath:: CompactPath

Bu işlev, [PathCompactPath](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
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

Ayrıntılar için bkz. [PathCompactPath](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw) .

## <a name="atlpathcompactpathex"></a><a name="compactpathex"></a>ATLPath:: CompactPathEx

Bu işlev, [PathCompactPathEx](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
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

Ayrıntılar için bkz. [PathCompactPathEx](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw) .

## <a name="atlpathfileexists"></a><a name="fileexists"></a>ATLPath:: FileExists

Bu işlev, [PathFileExists](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline BOOL FileExists(const char* pszPath);
inline BOOL FileExists(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [PathFileExists](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw) .

## <a name="atlpathfindextension"></a><a name="findextension"></a>ATLPath:: Findexgeri

Bu işlev, [Pathfindexgeri](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline char* FindExtension(const char* pszPath);
inline wchar_t* FindExtension(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [Pathfındexgeri](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw) .

## <a name="atlpathfindfilename"></a><a name="findfilename"></a>ATLPath:: FindFileName

Bu işlev, [PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline char* FindFileName(const char* pszPath);
inline wchar_t* FindFileName(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew) .

## <a name="atlpathgetdrivenumber"></a><a name="getdrivenumber"></a>ATLPath:: GetDriveNumber

Bu işlev, [PathGetDriveNumber](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline int GetDriveNumber(const char* pszPath);
inline int GetDriveNumber(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [PathGetDriveNumber](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw) .

## <a name="atlpathisdirectory"></a><a name="isdirectory"></a>ATLPath:: IsDirectory

Bu işlev [Pathisdirectory](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw)için aşırı yüklenmiş bir sarmalayıcıdır.

```cpp
inline BOOL IsDirectory(const char* pszPath);
inline BOOL IsDirectory(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. PathIsDirectory.

## <a name="atlpathisfilespec"></a><a name="isfilespec"></a>ATLPath:: ısdosyabelirtimi

Bu işlev [Pathisdosyabelirtimi](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline BOOL IsFileSpec(const char* pszPath);
inline BOOL IsFileSpec(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [Pathisdosyabelirtimi](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw) .

## <a name="atlpathisprefix"></a><a name="isprefix"></a>ATLPath:: Isprefıx

Bu işlev [Pathisprefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline BOOL IsPrefix(const char* pszPrefix, const char* pszPath);
inline BOOL IsPrefix(const wchar_t* pszPrefix, const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [Pathisprefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw) .

## <a name="atlpathisrelative"></a><a name="isrelative"></a>ATLPath:: ısgöreli

Bu işlev, [Pathısgöreli](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline BOOL IsRelative(const char* pszPath);
inline BOOL IsRelative(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [Pathısgöreli](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew) .

## <a name="atlpathisroot"></a><a name="isroot"></a>ATLPath:: IsRoot

Bu işlev, [Pathisroot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline BOOL IsRoot(const char* pszPath);
inline BOOL IsRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [PathIsRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw) .

## <a name="atlpathissameroot"></a><a name="issameroot"></a>ATLPath:: IsSameRoot

Bu işlev [Pathissameroot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline BOOL IsSameRoot(const char* pszPath1, const char* pszPath2);
inline BOOL IsSameRoot(const wchar_t* pszPath1, const wchar_t* pszPath2);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [Pathissameroot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw) .

## <a name="atlpathisunc"></a><a name="isunc"></a>ATLPath:: IsUnc

Bu işlev [Pathisunc](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline BOOL IsUNC(const char* pszPath);
inline BOOL IsUNC(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [Pathisunc](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw) .

## <a name="atlpathisuncserver"></a><a name="isuncserver"></a>ATLPath:: ısuncserver

Bu işlev [Pathisuncserver](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline BOOL IsUNCServer(const char* pszPath);
inline BOOL IsUNCServer(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [Pathisuncserver](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw) .

## <a name="atlpathisuncservershare"></a><a name="isuncservershare"></a>ATLPath:: ısuncservershare

Bu işlev [Pathisuncservershare](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline BOOL IsUNCServerShare(const char* pszPath);
inline BOOL IsUNCServerShare(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [Pathisuncservershare](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew) .

## <a name="atlpathmakepretty"></a><a name="makepretty"></a>ATLPath:: Makeoldukça

Bu işlev, [Pathmakeoldukça](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline BOOL MakePretty(char* pszPath);
inline BOOL MakePretty(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [Pathmakeoldukça](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw) .

## <a name="atlpathmatchspec"></a><a name="matchspec"></a>ATLPath:: MatchSpec

Bu işlev, [PathMatchSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline BOOL MatchSpec(const char* pszPath, const char* pszSpec);
inline BOOL MatchSpec(const wchar_t* pszPath, const wchar_t* pszSpec);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [PathMatchSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw) .

## <a name="atlpathquotespaces"></a><a name="quotespaces"></a>ATLPath:: QuoteSpaces

Bu işlev, [PathQuoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline void QuoteSpaces(char* pszPath);
inline void QuoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [PathQuoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw) .

## <a name="atlpathrelativepathto"></a><a name="relativepathto"></a>ATLPath:: RelativePathTo

Bu işlev [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
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

Ayrıntılar için bkz. [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow) .

## <a name="atlpathremoveargs"></a><a name="removeargs"></a>ATLPath:: RemoveArgs

Bu işlev [PathRemoveArgs](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline void RemoveArgs(char* pszPath);
inline void RemoveArgs(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [PathRemoveArgs](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw) .

## <a name="atlpathremovebackslash"></a><a name="removebackslash"></a>ATLPath:: Removeters eğik çizgi

Bu işlev [Pathremoveters eğik çizgi](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline char* RemoveBackslash(char* pszPath);
inline wchar_t* RemoveBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [Pathremoveters eğik çizgi](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw) .

## <a name="atlpathremoveblanks"></a><a name="removeblanks"></a>ATLPath:: Removeboşlar

Bu işlev, [Pathremoveboşluklar](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline void RemoveBlanks(char* pszPath);
inline void RemoveBlanks(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [Pathremoveboşlar](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw) .

## <a name="atlpathremoveextension"></a><a name="removeextension"></a>ATLPath:: RemoveExtension

Bu işlev [PathRemoveExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline void RemoveExtension(char* pszPath);
inline void RemoveExtension(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [PathRemoveExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw) .

## <a name="atlpathremovefilespec"></a><a name="removefilespec"></a>ATLPath:: Removedosyabelirtimi

Bu işlev, [Pathremovedosyabelirtimi](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline BOOL RemoveFileSpec(char* pszPath);
inline BOOL RemoveFileSpec(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [Pathremovedosyabelirtimi](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw) .

## <a name="atlpathrenameextension"></a><a name="renameextension"></a>ATLPath:: RenameExtension

Bu işlev [PathRenameExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline BOOL RenameExtension(char* pszPath, const char* pszExt);
inline BOOL RenameExtension(wchar_t* pszPath, const wchar_t* pszExt);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [PathRenameExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw) .

## <a name="atlpathskiproot"></a><a name="skiproot"></a>ATLPath:: SkipRoot

Bu işlev [PathSkipRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline char* SkipRoot(const char* pszPath);
inline wchar_t* SkipRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [PathSkipRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw) .

## <a name="atlpathstrippath"></a><a name="strippath"></a>ATLPath:: StripPath

Bu işlev, [PathStripPath](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline void StripPath(char* pszPath);
inline void StripPath(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [PathStripPath](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw) .

## <a name="atlpathstriptoroot"></a><a name="striptoroot"></a>ATLPath:: StripToRoot

Bu işlev, [PathStripToRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline BOOL StripToRoot(char* pszPath);
inline BOOL StripToRoot(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [PathStripToRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw) .

## <a name="atlpathunquotespaces"></a><a name="unquotespaces"></a>ATLPath:: UnquoteSpaces

Bu işlev, [PathUnquoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)için aşırı yüklenmiş bir sarmalayıcıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
inline void UnquoteSpaces(char* pszPath);
inline void UnquoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için bkz. [PathUnquoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw) .
