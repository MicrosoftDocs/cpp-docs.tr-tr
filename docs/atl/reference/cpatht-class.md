---
title: CPathT sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
dev_langs:
- C++
helpviewer_keywords:
- CPathT class
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60541891832a3d466f7396086ac0918108991582
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43753168"
---
# <a name="cpatht-class"></a>CPathT sınıfı

Bu sınıf, bir yol gösterir.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <typename StringType>
class CPathT
```

#### <a name="parameters"></a>Parametreler

*StringType*  
ATL/MFC string sınıfı yolu kullanmak için (bkz [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)).

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CPathT::PCXSTR](#pcxstr)|Bir sabit dize türü.|
|[CPathT::PXSTR](#pxstr)|Bir dize türü.|
|[CPathT::XCHAR](#xchar)|Bir karakter türü.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPathT::CPathT](#cpatht)|Yolu için oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPathT::AddBackslash](#addbackslash)|Doğru sözdizimi için bir yol oluşturmak için bir dizenin sonuna ters eğik çizgi eklemek için bu yöntemi çağırın.|
|[CPathT::AddExtension](#addextension)|Bir dosya uzantısı için bir yol eklemek için bu yöntemi çağırın.|
|[CPathT::Append](#append)|Geçerli bir dize eklemek için bu yöntemi çağırın.|
|[CPathT::BuildRoot](#buildroot)|Belirtilen sürücü numarasından kök yolu oluşturmak için bu yöntemi çağırın.|
|[CPathT::Canonicalize](#canonicalize)|Yol, kurallı biçimine dönüştürmek için bu yöntemi çağırın.|
|[CPathT::Combine](#combine)|Dizin adını temsil eden bir dize ve bir dosya yolu adı bir yola temsil eden bir dizeye bitiştirmek için bu yöntemi çağırın.|
|[CPathT::CommonPrefix](#commonprefix)|Belirtilen yol geçerli bir yol ile ortak bir öneki paylaşan olup olmadığını belirlemek için bu yöntemi çağırın.|
|[CPathT::CompactPath](#compactpath)|Üç nokta ile yol bileşenleri değiştirerek içinde belirtilen piksel genişliği sığdırmak için bir dosya yolu kesmek için bu yöntemi çağırın.|
|[CPathT::CompactPathEx](#compactpathex)|Bir dosya yolu, verilen sayıda karakteri içinde üç nokta ile yol bileşenleri değiştirerek uyacak şekilde kesmek için bu yöntemi çağırın.|
|[CPathT::FileExists](#fileexists)|Bu yol adı, dosyanın var olup olmadığını denetlemek için bu yöntemi çağırın.|
|[CPathT::FindExtension](#findextension)|Yol içinde dosya uzantısı konumunu bulmak için bu yöntemi çağırın.|
|[CPathT::FindFileName](#findfilename)|Konumu yolu dosya adını bulmak için bu yöntemi çağırın.|
|[CPathT::GetDriveNumber](#getdrivenumber)|'A'-'Z' aralığındaki bir sürücü harfi yolu arayın ve karşılık gelen sürücü sayısını döndürmek için bu yöntemi çağırın.|
|[CPathT::GetExtension](#getextension)|Dosya uzantısı yolu almak için bu yöntemi çağırın.|
|[CPathT::IsDirectory](#isdirectory)|Yolun geçerli bir dizin olup olmadığını denetlemek için bu yöntemi çağırın.|
|[CPathT::IsFileSpec](#isfilespec)|Arama yolu sınırlandıran herhangi bir karakter için bir yol için bu yöntemi çağırın (örneğin, ':' veya '\\'). Mevcut hiçbir yolu ayıran karakter varsa, yolu bir dosya belirtimi yol olarak değerlendirilir.|
|[CPathT::IsPrefix](#isprefix)|Bir yol geçirilen türü geçerli bir önek içerip içermediğini belirlemek için bu yöntemi çağırın *pszPrefix*.|
|[CPathT::IsRelative](#isrelative)|Yolun göreli olup olmadığını belirlemek için bu yöntemi çağırın.|
|[CPathT::IsRoot](#isroot)|Yol bir dizin kök olup olmadığını belirlemek için bu yöntemi çağırın.|
|[CPathT::IsSameRoot](#issameroot)|Başka bir yol, yolun geçerli bir ortak kök bileşeniyle sahip olup olmadığını belirlemek için bu yöntemi çağırın.|
|[CPathT::IsUNC](#isunc)|Yolun bir sunucu için geçerli bir UNC (Evrensel Adlandırma Kuralı) yolu olup olmadığını belirlemek için bu yöntemi çağırın ve paylaşın.|
|[CPathT::IsUNCServer](#isuncserver)|Yolun yalnızca bir sunucu için geçerli bir UNC (Evrensel Adlandırma Kuralı) yolu olup olmadığını belirlemek için bu yöntemi çağırın.|
|[CPathT::IsUNCServerShare](#isuncservershare)|Yolun geçerli bir UNC (Evrensel Adlandırma Kuralı) paylaşım yolu olup olmadığını belirlemek için bu yöntemi çağırın \\ \  *sunucu*\ *paylaşmak*.|
|[CPathT::MakePretty](#makepretty)|Tutarlı bir görünüm yolunu sağlamak için tüm küçük harf karakterleri bir yola dönüştürmek için bu yöntemi çağırın.|
|[CPathT::MatchSpec](#matchspec)|Yol için bir joker karakter eşleşme türü içeren bir dize aramak için bu yöntemi çağırın.|
|[CPathT::QuoteSpaces](#quotespaces)|Boşluk karakterleri içeriyorsa, yolu tırnak işaretleri içine alın için bu yöntemi çağırın.|
|[CPathT::RelativePathTo](#relativepathto)|Göreli bir yol bir dosya veya klasöründen diğerine oluşturmak için bu yöntemi çağırın.|
|[CPathT::RemoveArgs](#removeargs)|Herhangi bir komut satırı bağımsız değişkeni yolundan kaldırmak için bu yöntemi çağırın.|
|[CPathT::RemoveBackslash](#removebackslash)|Sondaki ters eğik çizgi yolundan kaldırmak için bu yöntemi çağırın.|
|[CPathT::RemoveBlanks](#removeblanks)|Yolundan başındaki ve sonundaki tüm boşlukları kaldırmak için bu yöntemi çağırın.|
|[CPathT::RemoveExtension](#removeextension)|Varsa yolundan dosya uzantısını kaldırmak için bu yöntemi çağırın.|
|[CPathT::RemoveFileSpec](#removefilespec)|Bunları varsa sondaki dosya adı ve ters eğik çizgi yolundan kaldırmak için bu yöntemi çağırın.|
|[CPathT::RenameExtension](#renameextension)|Yoldaki dosya adı uzantısı ile yeni bir uzantı değiştirmek için bu yöntemi çağırın. Dosya adı uzantısı içermiyorsa, uzantı dizenin sonuna eklenir.|
|[CPathT::SkipRoot](#skiproot)|Sürücü harfi veya UNC paylaşımı/yol bölümü yok sayılıyor yolunu ayrıştırmak için bu yöntemi çağırın.|
|[CPathT::StripPath](#strippath)|Tam yol ve dosya adı yol bölümü kaldırmak için bu yöntemi çağırın.|
|[CPathT::StripToRoot](#striptoroot)|Yol kök bilgileri dışında tüm parçalarını kaldırmak için bu yöntemi çağırın.|
|[CPathT::UnquoteSpaces](#unquotespaces)|Tırnak işaretleri başına ve sonuna bir yol kaldırmak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CPathT::operator const StringType &](#operator_const_stringtype_amp)|Bu işleç, bir dize gibi kabul edilmesi nesne sağlar.|
|[CPathT::operator CPathT::PCXSTR](#operator_cpatht__pcxstr)|Bu işleç, bir dize gibi kabul edilmesi nesne sağlar.|
|[CPathT::operator StringType &](#operator_stringtype)|Bu işleç, bir dize gibi kabul edilmesi nesne sağlar.|
|[CPathT::operator +=](#operator_add_eq)|Bu işleç, yolu bir dize ekler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPathT::m_strPath](#m_strpath)|Yolu.|

## <a name="remarks"></a>Açıklamalar

`CPath`, `CPathA`, ve `CPathW` öğesinin örneklemeleri olan `CPathT` gibi tanımlanır:

`typedef CPathT< CString > CPath;`

`typedef CPathT< CStringA > CPathA;`

`typedef CPathT< CStringW > CPathW;`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlpath.h

##  <a name="addbackslash"></a>  CPathT::AddBackslash

Doğru sözdizimi için bir yol oluşturmak için bir dizenin sonuna ters eğik çizgi eklemek için bu yöntemi çağırın. Yolun bir ters eğik zaten varsa, ters eğik çizgi yok eklenir.

```
void AddBackslash();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathAddBackSlash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha).

##  <a name="addextension"></a>  CPathT::AddExtension

Bir dosya uzantısı için bir yol eklemek için bu yöntemi çağırın.

```
BOOL AddExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>Parametreler

*pszExtension*  
Eklemek için dosya uzantısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona).

##  <a name="append"></a>  CPathT::Append

Geçerli bir dize eklemek için bu yöntemi çağırın.

```
BOOL Append(PCXSTR pszMore);
```

### <a name="parameters"></a>Parametreler

*pszMore*  
Eklenecek dize.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda).

##  <a name="buildroot"></a>  CPathT::BuildRoot

Belirtilen sürücü numarasından kök yolu oluşturmak için bu yöntemi çağırın.

```
void BuildRoot(int iDrive);
```

### <a name="parameters"></a>Parametreler

*iDrive*  
Sürücü sayısı (0, y:, 1, b ve benzeri).

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota).

##  <a name="canonicalize"></a>  CPathT::Canonicalize

Yol, kurallı biçimine dönüştürmek için bu yöntemi çağırın.

```
void Canonicalize();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea).

##  <a name="combine"></a>  CPathT::Combine

Dizin adını temsil eden bir dize ve bir dosya yolu adı bir yola temsil eden bir dizeye bitiştirmek için bu yöntemi çağırın.

```
void Combine(PCXSTR pszDir, PCXSTR  pszFile);
```

### <a name="parameters"></a>Parametreler

*pszDir*  
Dizin yolu.

*pszFile*  
Dosya yolu.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea).

##  <a name="commonprefix"></a>  CPathT::CommonPrefix

Belirtilen yol geçerli bir yol ile ortak bir öneki paylaşan olup olmadığını belirlemek için bu yöntemi çağırın.

```
CPathT<StringType> CommonPrefix(PCXSTR pszOther);
```

### <a name="parameters"></a>Parametreler

*pszOther*  
Karşılaştırma için geçerli bir yol.

### <a name="return-value"></a>Dönüş Değeri

Sık kullanılan öneki döndürür.

### <a name="remarks"></a>Açıklamalar

Bu tür bir önek biridir: "C:\\\\",".","...",".. \\\\". Daha fazla bilgi için [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa).

##  <a name="compactpath"></a>  CPathT::CompactPath

Üç nokta ile yol bileşenleri değiştirerek içinde belirtilen piksel genişliği sığdırmak için bir dosya yolu kesmek için bu yöntemi çağırın.

```
BOOL CompactPath(HDC hDC, UINT nWidth);
```

### <a name="parameters"></a>Parametreler

*hDC*  
Yazı tipi ölçümleri için kullanılan cihaz bağlamı.

*nWidth*  
Piksel cinsinden genişliği, dize sığacak kadar zorlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha).

##  <a name="compactpathex"></a>  CPathT::CompactPathEx

Bir dosya yolu, verilen sayıda karakteri içinde üç nokta ile yol bileşenleri değiştirerek uyacak şekilde kesmek için bu yöntemi çağırın.

```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```

### <a name="parameters"></a>Parametreler

*nMaxChars*  
Sondaki NULL karakter de dahil olmak üzere yeni dize içermesi gereken karakter sayısı.

*CertOpenStore*  
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa).

##  <a name="cpatht"></a>  CPathT::CPathT

Oluşturucu.

```
CPathT(PCXSTR pszPath);
CPathT(const CPathT<StringType>& path);
CPathT() throw();
```

### <a name="parameters"></a>Parametreler

*pszPath*  
Yol dizesi işaretçisi.

*Yolu*  
Yol dizesi.

##  <a name="fileexists"></a>  CPathT::FileExists

Bu yol adı, dosyanın var olup olmadığını denetlemek için bu yöntemi çağırın.

```
BOOL FileExists() const;
```

### <a name="return-value"></a>Dönüş Değeri

DOĞRU dosya, yanlış Aksi durumda olup olmadığını döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa).

##  <a name="findextension"></a>  CPathT::FindExtension

Yol içinde dosya uzantısı konumunu bulmak için bu yöntemi çağırın.

```
int FindExtension() const;
```

### <a name="return-value"></a>Dönüş Değeri

Konumunu döndürür "." uzantı önceki. Hiçbir uzantı bulunursa, -1 döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona).

##  <a name="findfilename"></a>  CPathT::FindFileName

Konumu yolu dosya adını bulmak için bu yöntemi çağırın.

```
int FindFileName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosya adı konumunu döndürür. Dosya adı bulunursa, -1 döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea).

##  <a name="getdrivenumber"></a>  CPathT::GetDriveNumber

'A'-'Z' aralığındaki bir sürücü harfi yolu arayın ve karşılık gelen sürücü sayısını döndürmek için bu yöntemi çağırın.

```
int GetDriveNumber() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aksi takdirde bir sürücü harfi veya -1 yol varsa, sürücü sayısı 0 25 ('A'-'Z' karşılık gelen) ile tamsayı olarak döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera).

##  <a name="getextension"></a>  CPathT::GetExtension

Dosya uzantısı yolu almak için bu yöntemi çağırın.

```
StringType GetExtension() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosya uzantısı döndürür.

##  <a name="isdirectory"></a>  CPathT::IsDirectory

Yolun geçerli bir dizin olup olmadığını denetlemek için bu yöntemi çağırın.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır olmayan bir değer (16) yolu bir dizin, aksi durumda FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Pathısdirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya).

##  <a name="isfilespec"></a>  CPathT::IsFileSpec

Arama yolu sınırlandıran herhangi bir karakter için bir yol için bu yöntemi çağırın (örneğin, ':' veya '\\'). Mevcut hiçbir yolu ayıran karakter varsa, yolu bir dosya belirtimi yol olarak değerlendirilir.

```
BOOL IsFileSpec() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol içinde hiçbir yolu ayıran karakter varsa TRUE ya da yolu ayıran karakter varsa FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Pathısfilespec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca).

##  <a name="isprefix"></a>  CPathT::IsPrefix

Bir yol geçirilen türü geçerli bir önek içerip içermediğini belirlemek için bu yöntemi çağırın *pszPrefix*.

```
BOOL IsPrefix(PCXSTR pszPrefix) const;
```

### <a name="parameters"></a>Parametreler

*pszPrefix*  
Aranacak önek. Bu tür bir önek biridir: "C:\\\\",".","...",".. \\\\".

### <a name="return-value"></a>Dönüş Değeri

Yol ön eki veya yanlış aksi içeriyorsa TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Pathısprefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa).

##  <a name="isrelative"></a>  CPathT::IsRelative

Yolun göreli olup olmadığını belirlemek için bu yöntemi çağırın.

```
BOOL IsRelative() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mutlak yol göreli ya da FALSE ise TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Pathısrelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea).

##  <a name="isroot"></a>  CPathT::IsRoot

Yol bir dizin kök olup olmadığını belirlemek için bu yöntemi çağırın.

```
BOOL IsRoot() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aksi halde bir kök veya yanlış yol olduğunda, TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Pathısroot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota).

##  <a name="issameroot"></a>  CPathT::IsSameRoot

Başka bir yol, yolun geçerli bir ortak kök bileşeniyle sahip olup olmadığını belirlemek için bu yöntemi çağırın.

```
BOOL IsSameRoot(PCXSTR pszOther) const;
```

### <a name="parameters"></a>Parametreler

*pszOther*  
Diğer bir yolu.

### <a name="return-value"></a>Dönüş Değeri

Her iki dize aynı kök bileşeni ya da FALSE aksi varsa TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Pathıssameroot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota).

##  <a name="isunc"></a>  CPathT::IsUNC

Yolun bir sunucu için geçerli bir UNC (Evrensel Adlandırma Kuralı) yolu olup olmadığını belirlemek için bu yöntemi çağırın ve paylaşın.

```
BOOL IsUNC() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yolun geçerli bir UNC yolu ya da FALSE olursa, TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Pathısunc](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca).

##  <a name="isuncserver"></a>  CPathT::IsUNCServer

Yolun yalnızca bir sunucu için geçerli bir UNC (Evrensel Adlandırma Kuralı) yolu olup olmadığını belirlemek için bu yöntemi çağırın.

```
BOOL IsUNCServer() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dize geçerli bir UNC yolu (paylaşım adı yok)'yalnızca bir sunucu için veya yanlış Aksi halde ise TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Pathısuncserver](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera).

##  <a name="isuncservershare"></a>  CPathT::IsUNCServerShare

Yolun geçerli bir UNC (Evrensel Adlandırma Kuralı) paylaşım yolu olup olmadığını belirlemek için bu yöntemi çağırın \\ \  *sunucu*\ *paylaşmak*.

```
BOOL IsUNCServerShare() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol biçiminde ise TRUE döndürür \\ \  *sunucu*\ *paylaşmak*, yanlış veya aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Pathısuncservershare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea).

##  <a name="m_strpath"></a>  CPathT::m_strPath

Yolu.

```
StringType m_strPath;
```

### <a name="remarks"></a>Açıklamalar

`StringType` Şablon parametresi `CPathT`.

##  <a name="makepretty"></a>  CPathT::MakePretty

Tutarlı bir görünüm yolunu sağlamak için tüm küçük harf karakterleri bir yola dönüştürmek için bu yöntemi çağırın.

```
BOOL MakePretty();
```

### <a name="return-value"></a>Dönüş Değeri

Yolun dönüştürdüyseniz TRUE veya FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya).

##  <a name="matchspec"></a>  CPathT::MatchSpec

Yol için bir joker karakter eşleşme türü içeren bir dize aramak için bu yöntemi çağırın.

```
BOOL MatchSpec(PCXSTR pszSpec) const;
```

### <a name="parameters"></a>Parametreler

*pszSpec*  
Aranacak dosya türü ile null ile sonlandırılmış bir dize işaretçisi. Örneğin, bir belge dosyası geçerli yolda bir dosya olup olmadığını sınamak için *pszSpec* ayarlanması gerekir "* .doc".

### <a name="return-value"></a>Dönüş Değeri

Dize eşleşmesi durumunda TRUE veya FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca).

##  <a name="operator_add_eq"></a>  CPathT::operator +=

Bu işleç, yolu bir dize ekler.

```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```

### <a name="parameters"></a>Parametreler

*pszMore*  
Eklenecek dize.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş yolunu döndürür.

##  <a name="operator_const_stringtype_amp"></a>  CPathT::operator const StringType &amp;

Bu işleç, bir dize gibi kabul edilmesi nesne sağlar.

```
operatorconst StringType&() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne tarafından yönetilen geçerli yolu temsil eden bir dize döndürür.

##  <a name="operator_cpatht__pcxstr"></a>  CPathT::operator CPathT::PCXSTR

Bu işleç, bir dize gibi kabul edilmesi nesne sağlar.

```
operatorPCXSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne tarafından yönetilen geçerli yolu temsil eden bir dize döndürür.

##  <a name="operator_stringtype__amp"></a>  CPathT::operator StringType &amp;

Bu işleç, bir dize gibi kabul edilmesi nesne sağlar.

```
operatorStringType&() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne tarafından yönetilen geçerli yolu temsil eden bir dize döndürür.

##  <a name="pcxstr"></a>  CPathT::PCXSTR

Bir sabit dize türü.

```
typedef StringType::PCXSTR PCXSTR;
```

### <a name="remarks"></a>Açıklamalar

`StringType` Şablon parametresi `CPathT`.

##  <a name="pxstr"></a>  CPathT::PXSTR

Bir dize türü.

```
typedef StringType::PXSTR PXSTR;
```

### <a name="remarks"></a>Açıklamalar

`StringType` Şablon parametresi `CPathT`.

##  <a name="quotespaces"></a>  CPathT::QuoteSpaces

Boşluk karakterleri içeriyorsa, yolu tırnak işaretleri içine alın için bu yöntemi çağırın.

```
void QuoteSpaces();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa).

##  <a name="relativepathto"></a>  CPathT::RelativePathTo

Göreli bir yol bir dosya veya klasöründen diğerine oluşturmak için bu yöntemi çağırın.

```
BOOL RelativePathTo(
    PCXSTR pszFrom,
    DWORD dwAttrFrom,
    PCXSTR pszTo,
    DWORD dwAttrTo);
```

### <a name="parameters"></a>Parametreler

*pszFrom*  
Göreli yol başlangıcı.

*dwAttrFrom*  
Dosya özniteliklerini *pszFrom*. Bu değer, FILE_ATTRIBUTE_DIRECTORY içeriyorsa *pszFrom* varsayılan bir dizin olması için; Aksi takdirde, *pszFrom* bir dosya olarak kabul edilir.

*pszTo*  
Bitiş noktası göreli yol.

*dwAttrTo*  
Dosya özniteliklerini *pszTo*. Bu değer, FILE_ATTRIBUTE_DIRECTORY içeriyorsa *pszTo* varsayılan bir dizin olması için; Aksi takdirde, *pszTo* bir dosya olarak kabul edilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa).

##  <a name="removeargs"></a>  CPathT::RemoveArgs

Herhangi bir komut satırı bağımsız değişkeni yolundan kaldırmak için bu yöntemi çağırın.

```
void RemoveArgs();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa).

##  <a name="removebackslash"></a>  CPathT::RemoveBackslash

Sondaki ters eğik çizgi yolundan kaldırmak için bu yöntemi çağırın.

```
void RemoveBackslash();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha).

##  <a name="removeblanks"></a>  CPathT::RemoveBlanks

Yolundan başındaki ve sonundaki tüm boşlukları kaldırmak için bu yöntemi çağırın.

```
void RemoveBlanks();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa).

##  <a name="removeextension"></a>  CPathT::RemoveExtension

Varsa yolundan dosya uzantısını kaldırmak için bu yöntemi çağırın.

```
void RemoveExtension();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona).

##  <a name="removefilespec"></a>  CPathT::RemoveFileSpec

Bunları varsa sondaki dosya adı ve ters eğik çizgi yolundan kaldırmak için bu yöntemi çağırın.

```
BOOL RemoveFileSpec();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca).

##  <a name="renameextension"></a>  CPathT::RenameExtension

Yoldaki dosya adı uzantısı ile yeni bir uzantı değiştirmek için bu yöntemi çağırın. Dosya adı uzantısı içermiyorsa, uzantı yolunun sonuna eklenir.

```
BOOL RenameExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>Parametreler

*pszExtension*  
Yeni dosya adı uzantısı, öncesinde bir "." karakter.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona).

##  <a name="skiproot"></a>  CPathT::SkipRoot

Sürücü harfi veya (Evrensel Adlandırma Kuralı) UNC paylaşımı/yol bölümü yok sayılıyor yolunu ayrıştırmak için bu yöntemi çağırın.

```
int SkipRoot() const;
```

### <a name="return-value"></a>Dönüş Değeri

(Sürücü harfi veya UNC paylaşımı /) kök izleyen yükleme kökü başına konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota).

##  <a name="strippath"></a>  CPathT::StripPath

Tam yol ve dosya adı yol bölümü kaldırmak için bu yöntemi çağırın.

```
void StripPath();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha).

##  <a name="striptoroot"></a>  CPathT::StripToRoot

Yol kök bilgileri dışında tüm parçalarını kaldırmak için bu yöntemi çağırın.

```
BOOL StripToRoot();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir sürücü harfi, TRUE döndürür bulundu yolunda ya da yanlış Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota).

##  <a name="unquotespaces"></a>  CPathT::UnquoteSpaces

Tırnak işaretleri başına ve sonuna bir yol kaldırmak için bu yöntemi çağırın.

```
void UnquoteSpaces();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa).

##  <a name="xchar"></a>  CPathT::XCHAR

Bir karakter türü.

```
typedef StringType::XCHAR XCHAR;
```

### <a name="remarks"></a>Açıklamalar

`StringType` Şablon parametresi `CPathT`.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfları](../../atl/reference/atl-classes.md)   
[CStringT Sınıfı](../../atl-mfc-shared/reference/cstringt-class.md)