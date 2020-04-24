---
title: CPathT Sınıfı
ms.date: 03/27/2019
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
helpviewer_keywords:
- CPathT class
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
ms.openlocfilehash: 76273e7fbfa50e610b437e11859821374413d008
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032140"
---
# <a name="cpatht-class"></a>CPathT Sınıfı

Bu sınıf bir yolu temsil eder.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <typename StringType>
class CPathT
```

#### <a name="parameters"></a>Parametreler

*StringType*<br/>
Yol için kullanılacak ATL/MFC dize sınıfı [(Bkz. CStringT).](../../atl-mfc-shared/reference/cstringt-class.md)

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CPathT::PCXSTR](#pcxstr)|Sabit bir dize türü.|
|[CPathT::PXSTR](#pxstr)|Bir dize türü.|
|[CPathT::XCHAR](#xchar)|Bir karakter türü.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CPathT::CPathT](#cpatht)|Yolun yapıcısı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPathT::AddBackslash](#addbackslash)|Bir yol için doğru sözdizimini oluşturmak için dize sonuna ters eğik çizgi eklemek için bu yöntemi çağırın.|
|[CPathT::AddExtension](#addextension)|Bir yola dosya uzantısı eklemek için bu yöntemi çağırın.|
|[CPathT::Ek](#append)|Geçerli yola bir dize eklemek için bu yöntemi çağırın.|
|[CPathT::BuildRoot](#buildroot)|Belirli bir sürücü numarasından kök yol oluşturmak için bu yöntemi çağırın.|
|[CPathT::Canonicalize](#canonicalize)|Yolu kanonik forma dönüştürmek için bu yöntemi arayın.|
|[CPathT::Birleştir](#combine)|Dizin adını ve dosya yolu adını temsil eden bir dizeyi tek bir yola dönüştürmek için bu yöntemi çağırın.|
|[CPathT::CommonPrefix](#commonprefix)|Belirtilen yolun geçerli yolla ortak bir önek paylaşıp paylaşmadığını belirlemek için bu yöntemi çağırın.|
|[CPathT::CompactPath](#compactpath)|Yol bileşenlerini elipslerle değiştirerek, belirli bir piksel genişliğine sığacak bir dosya yolunu parçalamak için bu yöntemi çağırın.|
|[CPathT::CompactPathEx](#compactpathex)|Yol bileşenlerini elipsile değiştirerek, belirli sayıda karaktere sığacak bir dosya yolunu truncate etmek için bu yöntemi çağırın.|
|[CPathT::FileExists](#fileexists)|Bu yol adındaki dosyanın var olup olmadığını denetlemek için bu yöntemi arayın.|
|[CPathT::FindExtension](#findextension)|Dosya uzantısının yol içindeki konumunu bulmak için bu yöntemi arayın.|
|[CPathT::FindFilename](#findfilename)|Dosya adının yol içindeki konumunu bulmak için bu yöntemi arayın.|
|[CPathT::GetDriveNumber](#getdrivenumber)|'A' ile 'Z' aralığında ki sürücü harfinin yolunu aramak ve ilgili sürücü numarasını döndürmek için bu yöntemi arayın.|
|[CPatht::GetExtension](#getextension)|Dosya uzantısını yoldan almak için bu yöntemi arayın.|
|[CPathT::İş Dizini](#isdirectory)|Yolun geçerli bir dizin olup olmadığını denetlemek için bu yöntemi arayın.|
|[Cpatht::IsfileSpec](#isfilespec)|Herhangi bir yol-delisi karakterler (örneğin, ':' veya '\\' ) için bir yol aramak için bu yöntemi arayın. Yol-delisi karakter yoksa, yol bir Dosya Spec yolu olarak kabul edilir.|
|[CPathT::Düzeltme](#isprefix)|Bir yolun *pszPrefix*tarafından geçirilen türün geçerli bir önekini içerip içermediğini belirlemek için bu yöntemi arayın.|
|[CPathT::Göreli](#isrelative)|Yolun göreceli olup olmadığını belirlemek için bu yöntemi arayın.|
|[CPathT::Kök](#isroot)|Yolun dizin kökü olup olmadığını belirlemek için bu yöntemi çağırın.|
|[Cpatht::Issameroot](#issameroot)|Başka bir yolun geçerli yolla ortak bir kök bileşeni olup olmadığını belirlemek için bu yöntemi çağırın.|
|[CPathT::IsUNC](#isunc)|Yolun bir sunucu ve paylaşım için geçerli bir UNC (evrensel adlandırma kuralı) yolu olup olmadığını belirlemek için bu yöntemi arayın.|
|[CPathT::IsUNCServer](#isuncserver)|Yolun yalnızca bir sunucu için geçerli bir UNC (evrensel adlandırma kuralı) yolu olup olmadığını belirlemek için bu yöntemi arayın.|
|[CPathT::IsUNCServerShare](#isuncservershare)|Yolun geçerli bir UNC (evrensel adlandırma kuralı) paylaşım yolu, \\ \  *sunucu*\ *paylaşımı*olup olmadığını belirlemek için bu yöntemi arayın.|
|[CPatht::MakePretty](#makepretty)|Yola tutarlı bir görünüm kazandırmak için bir yolu tüm küçük karakterlere dönüştürmek için bu yöntemi çağırın.|
|[Cpatht::MatchSpec](#matchspec)|Joker karakter eşleşmesi türü içeren bir dize için yolu aramak için bu yöntemi arayın.|
|[CPathT::Alıntı Alanları](#quotespaces)|Herhangi bir boşluk içeriyorsa, yolu tırnak işaretlerine baramak için bu yöntemi arayın.|
|[Cpatht::relativepathto](#relativepathto)|Bir dosya veya klasörden diğerine göreli bir yol oluşturmak için bu yöntemi çağırın.|
|[CPathT::RemoveArgs](#removeargs)|Herhangi bir komut satırı bağımsız değişkenini yoldan kaldırmak için bu yöntemi çağırın.|
|[CPathT::RemoveBackslash](#removebackslash)|Sondaki ters eğik çizgiyi yoldan kaldırmak için bu yöntemi arayın.|
|[CPathT::Boşlukları Kaldırma](#removeblanks)|Yoldaki tüm öncü ve sondaki boşlukları kaldırmak için bu yöntemi arayın.|
|[CPathT::RemoveExtension](#removeextension)|Varsa, dosya uzantısını yoldan kaldırmak için bu yöntemi arayın.|
|[CPatht::RemoveFileSpec](#removefilespec)|Bu yöntemi, uzaktaki dosya adını ve geri tepmeyi yoldan kaldırmak için çağırın.|
|[CPathT::RenameExtension](#renameextension)|Yoldaki dosya adı uzantısını yeni bir uzantıyla değiştirmek için bu yöntemi çağırın. Dosya adı bir uzantı içermiyorsa, uzantı dize sonuna eklenir.|
|[CPathT::SkipRoot](#skiproot)|Sürücü harfini veya UNC sunucu/pay yol parçalarını yok sayarak yolu ayrışdırmak için bu yöntemi çağırın.|
|[CPathT::StripPath](#strippath)|Tam nitelikli bir yolun ve dosya adının yol bölümünü kaldırmak için bu yöntemi arayın.|
|[Cpatht::Striptoroot](#striptoroot)|Kök bilgileri dışında yolun tüm bölümlerini kaldırmak için bu yöntemi arayın.|
|[CPathT::Alıntı Sızan Alanlar](#unquotespaces)|Bir yolun başından ve sonundan tırnak işaretlerini kaldırmak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CPathT::işleç const StringType &](#operator_const_stringtype_amp)|Bu işleç, nesnenin bir dize gibi ele alınmasına izin verir.|
|[CPathT::operatör CPathT::PCXSTR](#operator_cpatht__pcxstr)|Bu işleç, nesnenin bir dize gibi ele alınmasına izin verir.|
|[CPathT::operatör StringType &](#operator_stringtype_amp)|Bu işleç, nesnenin bir dize gibi ele alınmasına izin verir.|
|[CPathT::operatör +=](#operator_add_eq)|Bu işleç yola bir dize ekler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CPathT::m_strPath](#m_strpath)|Yol.|

## <a name="remarks"></a>Açıklamalar

`CPath`, `CPathA`, `CPathW` ve aşağıdaki `CPathT` gibi tanımlanan anlık vardır:

`typedef CPathT< CString > CPath;`

`typedef CPathT< CStringA > CPathA;`

`typedef CPathT< CStringW > CPathW;`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlpath.h

## <a name="cpathtaddbackslash"></a><a name="addbackslash"></a>CPathT::AddBackslash

Bir yol için doğru sözdizimini oluşturmak için dize sonuna ters eğik çizgi eklemek için bu yöntemi çağırın. Yol zaten bir geri dönüş varsa, hiçbir backslash eklenecektir.

```cpp
void AddBackslash();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Bkz. [PathAddBackSlash.](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw)

## <a name="cpathtaddextension"></a><a name="addextension"></a>CPathT::AddExtension

Bir yola dosya uzantısı eklemek için bu yöntemi çağırın.

```
BOOL AddExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>Parametreler

*pszUzatma*<br/>
Eklenecek dosya uzantısı.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. PathAddExtension.](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)

## <a name="cpathtappend"></a><a name="append"></a>CPathT::Ek

Geçerli yola bir dize eklemek için bu yöntemi çağırın.

```
BOOL Append(PCXSTR pszMore);
```

### <a name="parameters"></a>Parametreler

*pszDaha fazla*<br/>
Eklemek için dize.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathAppend'e](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)bakın.

## <a name="cpathtbuildroot"></a><a name="buildroot"></a>CPathT::BuildRoot

Belirli bir sürücü numarasından kök yol oluşturmak için bu yöntemi çağırın.

```cpp
void BuildRoot(int iDrive);
```

### <a name="parameters"></a>Parametreler

*Idrive*<br/>
Sürücü numarası (0, A:, 1 B:, vb.)

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. PathBuildRoot.](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)

## <a name="cpathtcanonicalize"></a><a name="canonicalize"></a>CPathT::Canonicalize

Yolu kanonik forma dönüştürmek için bu yöntemi arayın.

```cpp
void Canonicalize();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Bkz. [PathCanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew).

## <a name="cpathtcombine"></a><a name="combine"></a>CPathT::Birleştir

Dizin adını ve dosya yolu adını temsil eden bir dizeyi tek bir yola dönüştürmek için bu yöntemi çağırın.

```cpp
void Combine(PCXSTR pszDir, PCXSTR  pszFile);
```

### <a name="parameters"></a>Parametreler

*pszDir*<br/>
Dizin yolu.

*pszFile*<br/>
Dosya yolu.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Bkz. [PathCombine.](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew)

## <a name="cpathtcommonprefix"></a><a name="commonprefix"></a>CPathT::CommonPrefix

Belirtilen yolun geçerli yolla ortak bir önek paylaşıp paylaşmadığını belirlemek için bu yöntemi çağırın.

```
CPathT<StringType> CommonPrefix(PCXSTR pszOther);
```

### <a name="parameters"></a>Parametreler

*pszOther*<br/>
Geçerli olanla karşılaştırma yolu.

### <a name="return-value"></a>Dönüş Değeri

Ortak önek döndürür.

### <a name="remarks"></a>Açıklamalar

Önek şu türlerden biridir: "C:\\\\", ",.,.,.... \\\\". Daha fazla bilgi için [Bkz. PathCommonPrefix.](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)

## <a name="cpathtcompactpath"></a><a name="compactpath"></a>CPathT::CompactPath

Yol bileşenlerini elipslerle değiştirerek, belirli bir piksel genişliğine sığacak bir dosya yolunu parçalamak için bu yöntemi çağırın.

```
BOOL CompactPath(HDC hDC, UINT nWidth);
```

### <a name="parameters"></a>Parametreler

*Hdc*<br/>
Yazı tipi ölçümleri için kullanılan aygıt bağlamı.

*Nwidth*<br/>
Dize, piksel olarak, dize sığdırmak zorunda olacak genişliği.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathCompactPath'e](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)bakın.

## <a name="cpathtcompactpathex"></a><a name="compactpathex"></a>CPathT::CompactPathEx

Yol bileşenlerini elipsile değiştirerek, belirli sayıda karaktere sığacak bir dosya yolunu truncate etmek için bu yöntemi çağırın.

```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```

### <a name="parameters"></a>Parametreler

*nMaxChars*<br/>
Null karakterini sonlandırma dahil olmak üzere yeni dizede yer alan maksimum karakter sayısı.

*Dwflags*<br/>
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathCompactPathEx'e](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)bakın.

## <a name="cpathtcpatht"></a><a name="cpatht"></a>CPathT::CPathT

Oluşturucu.

```
CPathT(PCXSTR pszPath);
CPathT(const CPathT<StringType>& path);
CPathT() throw();
```

### <a name="parameters"></a>Parametreler

*pszPath*<br/>
Yol dizesine işaretçi.

*Yolu*<br/>
Yol dizesi.

## <a name="cpathtfileexists"></a><a name="fileexists"></a>CPathT::FileExists

Bu yol adındaki dosyanın var olup olmadığını denetlemek için bu yöntemi arayın.

```
BOOL FileExists() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosya varsa TRUE döndürür, aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Bkz. [PathFileExists](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw).

## <a name="cpathtfindextension"></a><a name="findextension"></a>CPathT::FindExtension

Dosya uzantısının yol içindeki konumunu bulmak için bu yöntemi arayın.

```
int FindExtension() const;
```

### <a name="return-value"></a>Dönüş Değeri

Uzantıdan önce "." konumunu döndürür. Uzantı bulunmazsa, -1 döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. PathFindExtension.](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)

## <a name="cpathtfindfilename"></a><a name="findfilename"></a>CPathT::FindFilename

Dosya adının yol içindeki konumunu bulmak için bu yöntemi arayın.

```
int FindFileName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosya adının konumunu döndürür. Dosya adı bulunmazsa ,1 döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. PathFindFileName.](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)

## <a name="cpathtgetdrivenumber"></a><a name="getdrivenumber"></a>CPathT::GetDriveNumber

'A' ile 'Z' aralığında ki sürücü harfinin yolunu aramak ve ilgili sürücü numarasını döndürmek için bu yöntemi arayın.

```
int GetDriveNumber() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sürücü numarasını 0'dan 25'e kadar tamsayı olarak döndürür (yolun bir sürücü harfi varsa 'A'dan 'Z'ye karşılık gelen) veya -1 aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. PathGetDriveNumber.](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)

## <a name="cpathtgetextension"></a><a name="getextension"></a>CPatht::GetExtension

Dosya uzantısını yoldan almak için bu yöntemi arayın.

```
StringType GetExtension() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosya uzantısını döndürür.

## <a name="cpathtisdirectory"></a><a name="isdirectory"></a>CPathT::İş Dizini

Yolun geçerli bir dizin olup olmadığını denetlemek için bu yöntemi arayın.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol bir dizin ise sıfır olmayan bir değer (16) döndürür, aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathIsDirectory'ye](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw)bakın.

## <a name="cpathtisfilespec"></a><a name="isfilespec"></a>Cpatht::IsfileSpec

Herhangi bir yol-delisi karakterler (örneğin, ':' veya '\\' ) için bir yol aramak için bu yöntemi arayın. Yol-delisi karakter yoksa, yol bir Dosya Spec yolu olarak kabul edilir.

```
BOOL IsFileSpec() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol içinde yol-delici karakter yoksa TRUE veya yol-delici karakterler varsa FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. PathIsFileSpec.](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)

## <a name="cpathtisprefix"></a><a name="isprefix"></a>CPathT::Düzeltme

Bir yolun *pszPrefix*tarafından geçirilen türün geçerli bir önekini içerip içermediğini belirlemek için bu yöntemi arayın.

```
BOOL IsPrefix(PCXSTR pszPrefix) const;
```

### <a name="parameters"></a>Parametreler

*pszPrefix*<br/>
Aranacak önek. Önek şu türlerden biridir: "C:\\\\", ",.,.,.... \\\\".

### <a name="return-value"></a>Dönüş Değeri

Yol öneki içeriyorsa TRUE veya aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. PathIsPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw).

## <a name="cpathtisrelative"></a><a name="isrelative"></a>CPathT::Göreli

Yolun göreceli olup olmadığını belirlemek için bu yöntemi arayın.

```
BOOL IsRelative() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol göreceliyse DOĞRU'yu döndürür veya mutlaksa FALSE'dur.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. PathIsRelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew).

## <a name="cpathtisroot"></a><a name="isroot"></a>CPathT::Kök

Yolun dizin kökü olup olmadığını belirlemek için bu yöntemi çağırın.

```
BOOL IsRoot() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol bir kökse veya başka türlü FALSE ise TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. PathIsRoot.](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)

## <a name="cpathtissameroot"></a><a name="issameroot"></a>Cpatht::Issameroot

Başka bir yolun geçerli yolla ortak bir kök bileşeni olup olmadığını belirlemek için bu yöntemi çağırın.

```
BOOL IsSameRoot(PCXSTR pszOther) const;
```

### <a name="parameters"></a>Parametreler

*pszOther*<br/>
Diğer yol.

### <a name="return-value"></a>Dönüş Değeri

Her iki dize de aynı kök bileşenine sahipse TRUE'yu döndürür veya başka türlü FALSE verir.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. PathIsSameRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw).

## <a name="cpathtisunc"></a><a name="isunc"></a>CPathT::IsUNC

Yolun bir sunucu ve paylaşım için geçerli bir UNC (evrensel adlandırma kuralı) yolu olup olmadığını belirlemek için bu yöntemi arayın.

```
BOOL IsUNC() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol geçerli bir UNC yoluysa TRUE veya başka türlü FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. PathIsUNC.](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)

## <a name="cpathtisuncserver"></a><a name="isuncserver"></a>CPathT::IsUNCServer

Yolun yalnızca bir sunucu için geçerli bir UNC (evrensel adlandırma kuralı) yolu olup olmadığını belirlemek için bu yöntemi arayın.

```
BOOL IsUNCServer() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dize yalnızca bir sunucu için geçerli bir UNC yoluysa (paylaşım adı yok) veya başka türlü FALSE varsa TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. PathIsUNCServer.](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw)

## <a name="cpathtisuncservershare"></a><a name="isuncservershare"></a>CPathT::IsUNCServerShare

Yolun geçerli bir UNC (evrensel adlandırma kuralı) paylaşım yolu, \\ \  *sunucu*\ *paylaşımı*olup olmadığını belirlemek için bu yöntemi arayın.

```
BOOL IsUNCServerShare() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol \\ \ form *sunucu*\ paylaşımında ysa TRUE veya false yoksa TRUE'yu döndürür.*share*

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. PathIsUNCServerShare.](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)

## <a name="cpathtm_strpath"></a><a name="m_strpath"></a>CPathT::m_strPath

Yol.

```
StringType m_strPath;
```

### <a name="remarks"></a>Açıklamalar

`StringType``CPathT`için şablon parametresi.

## <a name="cpathtmakepretty"></a><a name="makepretty"></a>CPatht::MakePretty

Yola tutarlı bir görünüm kazandırmak için bir yolu tüm küçük karakterlere dönüştürmek için bu yöntemi çağırın.

```
BOOL MakePretty();
```

### <a name="return-value"></a>Dönüş Değeri

Yol dönüştürüldüyse DOĞRU veya başka türlü FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathMakePretty'ye](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw)bakın.

## <a name="cpathtmatchspec"></a><a name="matchspec"></a>Cpatht::MatchSpec

Joker karakter eşleşmesi türü içeren bir dize için yolu aramak için bu yöntemi arayın.

```
BOOL MatchSpec(PCXSTR pszSpec) const;
```

### <a name="parameters"></a>Parametreler

*pszSpec*<br/>
Arama yapmak için dosya türüyle birlikte null-sonlandırılan bir dize işaretçi. Örneğin, geçerli yoldaki dosyanın DOC dosyası olup olmadığını sınamak için *pszSpec* "*.doc" olarak ayarlanmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Dize eşleşirse TRUE veya başka türlü FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathMatchSpec'e](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)bakın.

## <a name="cpathtoperator-"></a><a name="operator_add_eq"></a>CPathT::operatör +=

Bu işleç yola bir dize ekler.

```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```

### <a name="parameters"></a>Parametreler

*pszDaha fazla*<br/>
Eklemek için dize.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş yolu döndürür.

## <a name="cpathtoperator-const-stringtype-amp"></a><a name="operator_const_stringtype_amp"></a>CPathT::işleç const StringType&amp;

Bu işleç, nesnenin bir dize gibi ele alınmasına izin verir.

```
operator const StringType&() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne tarafından yönetilen geçerli yolu temsil eden bir dize döndürür.

## <a name="cpathtoperator-cpathtpcxstr"></a><a name="operator_cpatht__pcxstr"></a>CPathT::operatör CPathT::PCXSTR

Bu işleç, nesnenin bir dize gibi ele alınmasına izin verir.

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne tarafından yönetilen geçerli yolu temsil eden bir dize döndürür.

## <a name="cpathtoperator-stringtype-amp"></a><a name="operator_stringtype_amp"></a>CPathT::operatör StringType&amp;

Bu işleç, nesnenin bir dize gibi ele alınmasına izin verir.

```
operator StringType&() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne tarafından yönetilen geçerli yolu temsil eden bir dize döndürür.

## <a name="cpathtpcxstr"></a><a name="pcxstr"></a>CPathT::PCXSTR

Sabit bir dize türü.

```
typedef StringType::PCXSTR PCXSTR;
```

### <a name="remarks"></a>Açıklamalar

`StringType``CPathT`için şablon parametresi.

## <a name="cpathtpxstr"></a><a name="pxstr"></a>CPathT::PXSTR

Bir dize türü.

```
typedef StringType::PXSTR PXSTR;
```

### <a name="remarks"></a>Açıklamalar

`StringType``CPathT`için şablon parametresi.

## <a name="cpathtquotespaces"></a><a name="quotespaces"></a>CPathT::Alıntı Alanları

Herhangi bir boşluk içeriyorsa, yolu tırnak işaretlerine baramak için bu yöntemi arayın.

```cpp
void QuoteSpaces();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. PathQuoteSpaces.](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)

## <a name="cpathtrelativepathto"></a><a name="relativepathto"></a>Cpatht::relativepathto

Bir dosya veya klasörden diğerine göreli bir yol oluşturmak için bu yöntemi çağırın.

```
BOOL RelativePathTo(
    PCXSTR pszFrom,
    DWORD dwAttrFrom,
    PCXSTR pszTo,
    DWORD dwAttrTo);
```

### <a name="parameters"></a>Parametreler

*pszFrom*<br/>
Göreceli yolun başlangıcı.

*dwAttrFrom*<br/>
*pszFrom*Dosya öznitelikleri . Bu değer FILE_ATTRIBUTE_DIRECTORY içeriyorsa, *pszFrom* bir dizin olarak kabul edilir; aksi takdirde, *pszFrom* bir dosya olarak kabul edilir.

*pszTo*<br/>
Göreli yolun bitiş noktası.

*dwAttrTo*<br/>
*pszTo*Dosya öznitelikleri . Bu değer FILE_ATTRIBUTE_DIRECTORY içeriyorsa, *pszTo* bir dizin olarak kabul edilir; aksi takdirde, *pszTo* bir dosya olarak kabul edilir.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Bkz. [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow).

## <a name="cpathtremoveargs"></a><a name="removeargs"></a>CPathT::RemoveArgs

Herhangi bir komut satırı bağımsız değişkenini yoldan kaldırmak için bu yöntemi çağırın.

```cpp
void RemoveArgs();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathRemoveArgs'a](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)bakın.

## <a name="cpathtremovebackslash"></a><a name="removebackslash"></a>CPathT::RemoveBackslash

Sondaki ters eğik çizgiyi yoldan kaldırmak için bu yöntemi arayın.

```cpp
void RemoveBackslash();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Bkz. [PathRemoveBackslash.](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)

## <a name="cpathtremoveblanks"></a><a name="removeblanks"></a>CPathT::Boşlukları Kaldırma

Yoldaki tüm öncü ve sondaki boşlukları kaldırmak için bu yöntemi arayın.

```cpp
void RemoveBlanks();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Bkz. [PathRemoveBlanks.](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)

## <a name="cpathtremoveextension"></a><a name="removeextension"></a>CPathT::RemoveExtension

Varsa, dosya uzantısını yoldan kaldırmak için bu yöntemi arayın.

```cpp
void RemoveExtension();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. PathRemoveExtension.](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)

## <a name="cpathtremovefilespec"></a><a name="removefilespec"></a>CPatht::RemoveFileSpec

Bu yöntemi, uzaktaki dosya adını ve geri tepmeyi yoldan kaldırmak için çağırın.

```
BOOL RemoveFileSpec();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Bkz. [PathRemoveFileSpec.](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)

## <a name="cpathtrenameextension"></a><a name="renameextension"></a>CPathT::RenameExtension

Yoldaki dosya adı uzantısını yeni bir uzantıyla değiştirmek için bu yöntemi çağırın. Dosya adı bir uzantı içermiyorsa, uzantı yolun sonuna eklenir.

```
BOOL RenameExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>Parametreler

*pszUzatma*<br/>
Yeni dosya adı uzantısı, bir "." karakteri öncesinde.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. PathRenameExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw).

## <a name="cpathtskiproot"></a><a name="skiproot"></a>CPathT::SkipRoot

Sürücü harfini veya UNC (evrensel adlandırma kuralı) sunucu/paylaşım yolu bölümlerini yoksayarak yolu ayrıştırmak için bu yöntemi çağırın.

```
int SkipRoot() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kökü izleyen alt yolun başlangıcının konumunu döndürür (sürücü harfi veya UNC sunucusu/paylaşımı).

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. PathSkipRoot.](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)

## <a name="cpathtstrippath"></a><a name="strippath"></a>CPathT::StripPath

Tam nitelikli bir yolun ve dosya adının yol bölümünü kaldırmak için bu yöntemi arayın.

```cpp
void StripPath();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathStripPath'e](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)bakın.

## <a name="cpathtstriptoroot"></a><a name="striptoroot"></a>Cpatht::Striptoroot

Kök bilgileri dışında yolun tüm bölümlerini kaldırmak için bu yöntemi arayın.

```
BOOL StripToRoot();
```

### <a name="return-value"></a>Dönüş Değeri

Yolda geçerli bir sürücü mektubu bulunursa TRUE veya başka bir şekilde FALSE bulunursa TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [PathStripToRoot'a](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)bakın.

## <a name="cpathtunquotespaces"></a><a name="unquotespaces"></a>CPathT::Alıntı Sızan Alanlar

Bir yolun başından ve sonundan tırnak işaretlerini kaldırmak için bu yöntemi çağırın.

```cpp
void UnquoteSpaces();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Bkz. [PathUnquoteSpaces.](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)

## <a name="cpathtxchar"></a><a name="xchar"></a>CPathT::XCHAR

Bir karakter türü.

```
typedef StringType::XCHAR XCHAR;
```

### <a name="remarks"></a>Açıklamalar

`StringType``CPathT`için şablon parametresi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../atl/reference/atl-classes.md)<br/>
[CStringT Sınıfı](../../atl-mfc-shared/reference/cstringt-class.md)
