---
title: ATL yol işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d5b3677ab256e6d1b3e88f5bc71c8b9c7b097b2
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43753298"
---
# <a name="atl-path-functions"></a>ATL yol işlevleri

ATL yol biçiminde işlemek için ATLPath sınıfı sağlar [CPathT](cpatht-class.md). Bu kod atlpath.h içinde bulunabilir.

### <a name="related-classes"></a>İlgili sınıflar

|||
|-|-|
|[CPathT Sınıfı](cpatht-class.md)|Bu sınıf, bir yol gösterir.|

### <a name="related-typedefs"></a>İlgili tür tanımları

|||
|-|-|
|`CPath`|Bir alt uzmanlaşması [CPathT](cpatht-class.md) kullanarak `CString`.|
|`CPathA`|Bir alt uzmanlaşması [CPathT](cpatht-class.md) kullanarak `CStringA`.|
|`CPathW`|Bir alt uzmanlaşması [CPathT](cpatht-class.md) kullanarak `CStringW`.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[ATLPath::AddBackslash](#addbackslash)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha).|
|[ATLPath::AddExtension](#addextension)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona).|
|[ATLPath::Append](#append)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda).|
|[ATLPath::BuildRoot](#buildroot)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota).|
|[ATLPath::Canonicalize](#canonicalize)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea).|
|[ATLPath::Combine](#combine)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea).|
|[ATLPath::CommonPrefix](#commonprefix)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa).|
|[ATLPath::CompactPath](#compactpath)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha).|
|[ATLPath::CompactPathEx](#compactpathex)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa).|
|[ATLPath::FileExists](#fileexists)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa).|
|[ATLPath::FindExtension](#findextension)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona).|
|[ATLPath::FindFileName](#findfilename)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea).|
|[ATLPath::GetDriveNumber](#getdrivenumber)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera).|
|[ATLPath::IsDirectory](#isdirectory)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısdirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya).|
|[ATLPath::IsFileSpec](#isfilespec)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısfilespec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca).|
|[ATLPath::IsPrefix](#isprefix)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısprefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa).|
|[ATLPath::IsRelative](#isrelative)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısrelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea).|
|[ATLPath::IsRoot](#isroot)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısroot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota).|
|[ATLPath::IsSameRoot](#issameroot)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathıssameroot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota).|
|[ATLPath::IsUNC](#isunc)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısunc](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca).|
|[ATLPath::IsUNCServer](#isuncserver)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısuncserver](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera).|
|[ATLPath::IsUNCServerShare](#isuncservershare)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısuncservershare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea).|
|[ATLPath::MakePretty](#makepretty)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya).|
|[ATLPath::MatchSpec](#matchspec)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca).|
|[ATLPath::QuoteSpaces](#quotespaces)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa).|
|[ATLPath::RelativePathTo](#relativepathto)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa).|
|[ATLPath::RemoveArgs](#removeargs)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa).|
|[ATLPath::RemoveBackslash](#removebackslash)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha).|
|[ATLPath::RemoveBlanks](#removeblanks)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa).|
|[ATLPath::RemoveExtension](#removeextension)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona).|
|[ATLPath::RemoveFileSpec](#removefilespec)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca).|
|[ATLPath::RenameExtension](#renameextension)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona).|
|[ATLPath::SkipRoot](#skiproot)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota).|
|[ATLPath::StripPath](#strippath)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha).|
|[ATLPath::StripToRoot](#striptoroot)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota).|
|[ATLPath::UnquoteSpaces](#unquotespaces)|Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa).|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlpath.h

## <a name="addbackslash"></a> ATLPath::AddBackSlash

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha).

### <a name="syntax"></a>Sözdizimi

```
inline char* AddBackslash(char* pszPath);
inline wchar_t* AddBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha) Ayrıntılar için.

## <a name="addextension"></a> ATLPath::AddExtension

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona).

### <a name="syntax"></a>Sözdizimi

```
inline BOOL AddExtension(char* pszPath, const char* pszExtension);
inline BOOL AddExtension(wchar_t* pszPath, const wchar_t* pszExtension);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona) Ayrıntılar için.

## <a name="append"></a> ATLPath::Append

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda).

### <a name="syntax"></a>Sözdizimi

```
inline BOOL Append(char* pszPath, const char* pszMore);
inline BOOL Append(wchar_t* pszPath, const wchar_t* pszMore);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda) Ayrıntılar için.

## <a name="buildroot"></a> ATLPath::BuildRoot

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota).

### <a name="syntax"></a>Sözdizimi

```
inline char* BuildRoot(char* pszPath, int iDrive);
inline wchar_t* BuildRoot(wchar_t* pszPath, int iDrive);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota) Ayrıntılar için.

## <a name="canonicalize"></a> ATLPath::Canonicalize

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea).

### <a name="syntax"></a>Sözdizimi

```
inline BOOL Canonicalize(char* pszDest, const char* pszSrc);
inline BOOL Canonicalize(wchar_t* pszDest, const wchar_t* pszSrc);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea) Ayrıntılar için.

## <a name="combine"></a> ATLPath::Combine

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea).

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

## <a name="commonprefix"></a> ATLPath::CommonPrefix

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa).

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

Bkz: [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa) Ayrıntılar için.

## <a name="compactpath"></a> ATLPath::CompactPath

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha).

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

Bkz: [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha) Ayrıntılar için.

## <a name="compactpathex"></a> ATLPath::CompactPathEx

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa).

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

Bkz: [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa) Ayrıntılar için.

## <a name="fileexists"></a> ATLPath::FileExists

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa).

### <a name="syntax"></a>Sözdizimi

```
inline BOOL FileExists(const char* pszPath);
inline BOOL FileExists(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa) Ayrıntılar için.

## <a name="findextension"></a> ATLPath::FindExtension

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona).

### <a name="syntax"></a>Sözdizimi

```
inline char* FindExtension(const char* pszPath);
inline wchar_t* FindExtension(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona) Ayrıntılar için.

## <a name="findfilename"></a> ATLPath::FindFileName

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea).

### <a name="syntax"></a>Sözdizimi

```
inline char* FindFileName(const char* pszPath);
inline wchar_t* FindFileName(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea) Ayrıntılar için.

## <a name="getdrivenumber"></a> ATLPath::GetDriveNumber

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera).

### <a name="syntax"></a>Sözdizimi

```
inline int GetDriveNumber(const char* pszPath);
inline int GetDriveNumber(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera) Ayrıntılar için.

## <a name="isdirectory"></a>  ATLPath::IsDirectory

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısdirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya).

```
inline BOOL IsDirectory(const char* pszPath);
inline BOOL IsDirectory(const wchar_t* pszPath);
```
### <a name="remarks"></a>Açıklamalar

Pathısdirectory Ayrıntılar için bkz.

## <a name="isfilespec"></a> ATLPath::IsFileSpec

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısfilespec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca).

### <a name="syntax"></a>Sözdizimi

```
inline BOOL IsFileSpec(const char* pszPath);
inline BOOL IsFileSpec(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [Pathısfilespec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca) Ayrıntılar için.

## <a name="isprefix"></a> ATLPath::IsPrefix

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısprefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa).

### <a name="syntax"></a>Sözdizimi

```
inline BOOL IsPrefix(const char* pszPrefix, const char* pszPath);
inline BOOL IsPrefix(const wchar_t* pszPrefix, const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [Pathısprefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa) Ayrıntılar için.

## <a name="isrelative"></a> ATLPath::IsRelative

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısrelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea).

### <a name="syntax"></a>Sözdizimi

```
inline BOOL IsRelative(const char* pszPath);
inline BOOL IsRelative(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [Pathısrelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea) Ayrıntılar için.

## <a name="isroot"></a> ATLPath::IsRoot

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısroot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota).

### <a name="syntax"></a>Sözdizimi

```
inline BOOL IsRoot(const char* pszPath);
inline BOOL IsRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [Pathısroot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota) Ayrıntılar için.

## <a name="issameroot"></a> ATLPath::IsSameRoot

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathıssameroot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota).

### <a name="syntax"></a>Sözdizimi

```
inline BOOL IsSameRoot(const char* pszPath1, const char* pszPath2);
inline BOOL IsSameRoot(const wchar_t* pszPath1, const wchar_t* pszPath2);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [Pathıssameroot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota) Ayrıntılar için.

## <a name="isunc"></a> ATLPath::IsUNC

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısunc](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca).

### <a name="syntax"></a>Sözdizimi

```
inline BOOL IsUNC(const char* pszPath);
inline BOOL IsUNC(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [Pathısunc](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca) Ayrıntılar için.

## <a name="isuncserver"></a> ATLPath::IsUNCServer

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısuncserver](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera).

### <a name="syntax"></a>Sözdizimi

```
inline BOOL IsUNCServer(const char* pszPath);
inline BOOL IsUNCServer(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [Pathısuncserver](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera) Ayrıntılar için.

## <a name="isuncservershare"></a> ATLPath::IsUNCServerShare

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısuncservershare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea).

### <a name="syntax"></a>Sözdizimi

```
inline BOOL IsUNCServerShare(const char* pszPath);
inline BOOL IsUNCServerShare(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [Pathısuncservershare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea) Ayrıntılar için.

## <a name="makepretty"></a> ATLPath::MakePretty

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya).

### <a name="syntax"></a>Sözdizimi

```
inline BOOL MakePretty(char* pszPath);
inline BOOL MakePretty(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya) Ayrıntılar için.

## <a name="matchspec"></a> ATLPath::MatchSpec

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca).

### <a name="syntax"></a>Sözdizimi

```
inline BOOL MatchSpec(const char* pszPath, const char* pszSpec);
inline BOOL MatchSpec(const wchar_t* pszPath, const wchar_t* pszSpec);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca) Ayrıntılar için.

## <a name="quotespaces"></a> ATLPath::QuoteSpaces

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa).

### <a name="syntax"></a>Sözdizimi

```
inline void QuoteSpaces(char* pszPath);
inline void QuoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa) Ayrıntılar için.

## <a name="relativepathto"></a> ATLPath::RelativePathTo

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa).

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

Bkz: [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa) Ayrıntılar için.

## <a name="removeargs"></a> ATLPath::RemoveArgs

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa).

### <a name="syntax"></a>Sözdizimi

```
inline void RemoveArgs(char* pszPath);
inline void RemoveArgs(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa) Ayrıntılar için.

## <a name="removebackslash"></a> ATLPath::RemoveBackslash

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha).

### <a name="syntax"></a>Sözdizimi

```
inline char* RemoveBackslash(char* pszPath);
inline wchar_t* RemoveBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha) Ayrıntılar için.

## <a name="removeblanks"></a> ATLPath::RemoveBlanks

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa).

### <a name="syntax"></a>Sözdizimi

```
inline void RemoveBlanks(char* pszPath);
inline void RemoveBlanks(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa) Ayrıntılar için.

## <a name="removeextension"></a> ATLPath::RemoveExtension

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona).

### <a name="syntax"></a>Sözdizimi

```
inline void RemoveExtension(char* pszPath);
inline void RemoveExtension(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona) Ayrıntılar için.

## <a name="removefilespec"></a> ATLPath::RemoveFileSpec

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca).

### <a name="syntax"></a>Sözdizimi

```
inline BOOL RemoveFileSpec(char* pszPath);
inline BOOL RemoveFileSpec(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca) Ayrıntılar için.

## <a name="renameextension"></a> ATLPath::RenameExtension

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona).

### <a name="syntax"></a>Sözdizimi

```
inline BOOL RenameExtension(char* pszPath, const char* pszExt);
inline BOOL RenameExtension(wchar_t* pszPath, const wchar_t* pszExt);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona) Ayrıntılar için.

## <a name="skiproot"></a> ATLPath::SkipRoot

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota).

### <a name="syntax"></a>Sözdizimi

```
inline char* SkipRoot(const char* pszPath);
inline wchar_t* SkipRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota) Ayrıntılar için.

## <a name="strippath"></a> ATLPath::StripPath

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha).

### <a name="syntax"></a>Sözdizimi

```
inline void StripPath(char* pszPath);
inline void StripPath(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha) Ayrıntılar için.

## <a name="striptoroot"></a> ATLPath::StripToRoot

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota).

### <a name="syntax"></a>Sözdizimi

```
inline BOOL StripToRoot(char* pszPath);
inline BOOL StripToRoot(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota) Ayrıntılar için.

## <a name="unquotespaces"></a> ATLPath::UnquoteSpaces

Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa).

### <a name="syntax"></a>Sözdizimi

```
inline void UnquoteSpaces(char* pszPath);
inline void UnquoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa) Ayrıntılar için.

