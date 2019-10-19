---
title: CPathT sınıfı
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
ms.openlocfilehash: ba1c831d772deef34449d17adc2c8e7a6f90eaef
ms.sourcegitcommit: 8178d22701047d24f69f10d01ba37490e3d67241
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2019
ms.locfileid: "69496611"
---
# <a name="cpatht-class"></a>CPathT sınıfı

Bu sınıf bir yolu temsil eder.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <typename StringType>
class CPathT
```

#### <a name="parameters"></a>Parametreler

*StringType*<br/>
Yol için kullanılacak ATL/MFC dize sınıfı (bkz. [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)).

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Name|Açıklama|
|----------|-----------------|
|[CPathT::P CXSTR](#pcxstr)|Sabit bir dize türü.|
|[CPathT::P XSTR](#pxstr)|Bir dize türü.|
|[CPathT:: XCHAR](#xchar)|Bir karakter türü.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[CPathT:: CPathT](#cpatht)|Yol için Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[CPathT:: Addters eğik çizgi](#addbackslash)|Bir yol için doğru sözdizimi oluşturmak üzere bir dizenin sonuna bir ters eğik çizgi eklemek için bu yöntemi çağırın.|
|[CPathT:: Addexgeri](#addextension)|Bir yola dosya uzantısı eklemek için bu yöntemi çağırın.|
|[CPathT:: Append](#append)|Geçerli yola bir dize eklemek için bu yöntemi çağırın.|
|[CPathT:: BuildRoot](#buildroot)|Verilen bir sürücü numarasından bir kök yolu oluşturmak için bu yöntemi çağırın.|
|[CPathT:: canonicalize](#canonicalize)|Yolu kurallı biçime dönüştürmek için bu yöntemi çağırın.|
|[CPathT:: birleştirin](#combine)|Dizin adını temsil eden bir dizeyi ve dosya yolu adını tek bir yolda temsil eden dizeyi birleştirmek için bu yöntemi çağırın.|
|[CPathT:: CommonPrefix](#commonprefix)|Belirtilen yolun geçerli yol ile ortak bir ön eki payanıp paylaşmadığını öğrenmek için bu yöntemi çağırın.|
|[CPathT:: CompactPath](#compactpath)|Yol bileşenlerini üç noktayla değiştirerek bir dosya yolunu belirli bir piksel genişliğine sığacak şekilde kesmek için bu yöntemi çağırın.|
|[CPathT:: CompactPathEx](#compactpathex)|Yol bileşenlerini üç noktayla değiştirerek, bir dosya yolunu belirli sayıda karakter içine sığacak şekilde kesmek için bu yöntemi çağırın.|
|[CPathT:: FileExists](#fileexists)|Bu yol adında dosyanın mevcut olup olmadığını denetlemek için bu yöntemi çağırın.|
|[CPathT:: Findexgeri](#findextension)|Yol içinde dosya uzantısının konumunu bulmak için bu yöntemi çağırın.|
|[CPathT:: FindFileName](#findfilename)|Yolun içindeki dosya adının konumunu bulmak için bu yöntemi çağırın.|
|[CPathT:: GetDriveNumber](#getdrivenumber)|' A '-' Z ' aralığı içindeki bir sürücü harfinin yolunu aramak ve karşılık gelen sürücü numarasını döndürmek için bu yöntemi çağırın.|
|[CPathT:: GetExtension](#getextension)|Yoldan dosya uzantısını almak için bu yöntemi çağırın.|
|[CPathT:: IsDirectory](#isdirectory)|Yolun geçerli bir dizin olup olmadığını denetlemek için bu yöntemi çağırın.|
|[CPathT:: ısdosyabelirtimi](#isfilespec)|Yol sınırlayan karakterlerin yolunu aramak için bu yöntemi çağırın (örneğin, ': ' veya ' \\ '). Yol sınırlayan karakter yoksa, yol bir dosya belirtimi yolu olarak kabul edilir.|
|[CPathT:: IsPrefix](#isprefix)|Bir yolun *pszPrefix*tarafından geçirilen türün geçerli bir önekini içerip içermediğini anlamak için bu yöntemi çağırın.|
|[CPathT:: ısgöreli](#isrelative)|Yolun göreli olup olmadığını anlamak için bu yöntemi çağırın.|
|[CPathT:: IsRoot](#isroot)|Yolun bir dizin kökü olup olmadığını anlamak için bu yöntemi çağırın.|
|[CPathT:: IsSameRoot](#issameroot)|Başka bir yolun geçerli yol ile ortak bir kök bileşene sahip olup olmadığını anlamak için bu yöntemi çağırın.|
|[CPathT:: IsUnc](#isunc)|Yolun bir sunucu ve paylaşma için geçerli bir UNC (evrensel adlandırma kuralı) yolu olup olmadığını öğrenmek için bu yöntemi çağırın.|
|[CPathT:: ısuncserver](#isuncserver)|Yolun yalnızca bir sunucu için geçerli bir UNC (evrensel adlandırma kuralı) yolu olup olmadığını öğrenmek için bu yöntemi çağırın.|
|[CPathT:: ısuncservershare](#isuncservershare)|Yolun geçerli bir UNC (evrensel adlandırma kuralı) paylaşma yolu olup olmadığını (\\ \ *server* \ *paylaşımının*mi olduğunu öğrenmek için bu yöntemi çağırın.|
|[CPathT:: Makeoldukça](#makepretty)|Yolun tutarlı bir görünüm sağlamak için bir yolu tüm küçük harfli karakterlere dönüştürmek için bu yöntemi çağırın.|
|[CPathT:: MatchSpec](#matchspec)|Joker karakter eşleşme türü içeren bir dizenin yolunu aramak için bu yöntemi çağırın.|
|[CPathT:: QuoteSpaces](#quotespaces)|Herhangi bir boşluk içeriyorsa, yolu tırnak işaretleri içine almak için bu yöntemi çağırın.|
|[CPathT:: RelativePathTo](#relativepathto)|Bir dosyadan veya klasörden diğerine göreli yol oluşturmak için bu yöntemi çağırın.|
|[CPathT:: RemoveArgs](#removeargs)|Yoldaki komut satırı bağımsız değişkenlerini kaldırmak için bu yöntemi çağırın.|
|[CPathT:: Removeters eğik çizgi](#removebackslash)|Yolun sonundaki ters eğik çizgiyi kaldırmak için bu yöntemi çağırın.|
|[CPathT:: Removeboşlar](#removeblanks)|Yoldan baştaki ve sondaki boşlukları kaldırmak için bu yöntemi çağırın.|
|[CPathT:: RemoveExtension](#removeextension)|Dosya uzantısını yoldan kaldırmak için bu yöntemi çağırın.|
|[CPathT:: Removedosyabelirtimi](#removefilespec)|Bu yöntemi, varsa sonunda dosya adını ve ters eğik çizgiyi kaldırmak için çağırın.|
|[CPathT:: RenameExtension](#renameextension)|Yoldaki dosya adı uzantısını yeni bir uzantıyla değiştirmek için bu yöntemi çağırın. Dosya adı bir uzantı içermiyorsa, uzantı dizenin sonuna iliştirilir.|
|[CPathT:: SkipRoot](#skiproot)|Sürücü harfi veya UNC sunucu/paylaşma yolu parçalarını yoksayarak bir yolu ayrıştırmak için bu yöntemi çağırın.|
|[CPathT:: StripPath](#strippath)|Tam nitelenmiş yolun ve dosya adının yol bölümünü kaldırmak için bu yöntemi çağırın.|
|[CPathT:: StripToRoot](#striptoroot)|Kök bilgileri hariç yolun tüm bölümlerini kaldırmak için bu yöntemi çağırın.|
|[CPathT:: UnquoteSpaces](#unquotespaces)|Yolun başındaki ve sonundaki tırnak işaretlerini kaldırmak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Name|Açıklama|
|----------|-----------------|
|[CPathT:: operator const StringType &](#operator_const_stringtype_amp)|Bu işleç nesnenin bir dize gibi işlenmesine izin verir.|
|[CPathT:: operator CPathT::P CXSTR](#operator_cpatht__pcxstr)|Bu işleç nesnenin bir dize gibi işlenmesine izin verir.|
|[CPathT:: operator StringType &](#operator_stringtype_amp)|Bu işleç nesnenin bir dize gibi işlenmesine izin verir.|
|[CPathT:: operator + =](#operator_add_eq)|Bu işleç yola bir dize ekler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Name|Açıklama|
|----------|-----------------|
|[CPathT:: m_strPath](#m_strpath)|Yol.|

## <a name="remarks"></a>Açıklamalar

`CPath`, `CPathA` ve `CPathW`, aşağıdaki gibi tanımlanan `CPathT` örneklemelerdir:

`typedef CPathT< CString > CPath;`

`typedef CPathT< CStringA > CPathA;`

`typedef CPathT< CStringW > CPathW;`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlpath. h

##  <a name="addbackslash"></a>CPathT:: Addters eğik çizgi

Bir yol için doğru sözdizimi oluşturmak üzere bir dizenin sonuna bir ters eğik çizgi eklemek için bu yöntemi çağırın. Yolun sonunda bir ters eğik çizgi varsa ters eğik çizgi eklenmez.

```
void AddBackslash();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Pathaddters eğik çizgi](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw).

##  <a name="addextension"></a>CPathT:: Addexgeri

Bir yola dosya uzantısı eklemek için bu yöntemi çağırın.

```
BOOL AddExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>Parametreler

*pszExtension*<br/>
Eklenecek dosya uzantısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Pathaddexgeri](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw).

##  <a name="append"></a>CPathT:: Append

Geçerli yola bir dize eklemek için bu yöntemi çağırın.

```
BOOL Append(PCXSTR pszMore);
```

### <a name="parameters"></a>Parametreler

*pszMore*<br/>
Eklenecek dize.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathAppend](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw).

##  <a name="buildroot"></a>CPathT:: BuildRoot

Verilen bir sürücü numarasından bir kök yolu oluşturmak için bu yöntemi çağırın.

```
void BuildRoot(int iDrive);
```

### <a name="parameters"></a>Parametreler

*IDrive*<br/>
Sürücü numarası (0:, 1, B:, vb.).

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathBuildRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw).

##  <a name="canonicalize"></a>CPathT:: canonicalize

Yolu kurallı biçime dönüştürmek için bu yöntemi çağırın.

```
void Canonicalize();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathCanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew).

##  <a name="combine"></a>CPathT:: birleştirin

Dizin adını temsil eden bir dizeyi ve dosya yolu adını tek bir yolda temsil eden dizeyi birleştirmek için bu yöntemi çağırın.

```
void Combine(PCXSTR pszDir, PCXSTR  pszFile);
```

### <a name="parameters"></a>Parametreler

*pszDir*<br/>
Dizin yolu.

*pszFile*<br/>
Dosya yolu.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Pathbirleştirme](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew).

##  <a name="commonprefix"></a>CPathT:: CommonPrefix

Belirtilen yolun geçerli yol ile ortak bir ön eki payanıp paylaşmadığını öğrenmek için bu yöntemi çağırın.

```
CPathT<StringType> CommonPrefix(PCXSTR pszOther);
```

### <a name="parameters"></a>Parametreler

*pszOther*<br/>
Geçerli bir Karşılaştırılacak yol.

### <a name="return-value"></a>Dönüş Değeri

Ortak ön eki döndürür.

### <a name="remarks"></a>Açıklamalar

Ön ek şu türlerden biridir: "C: \\ \\", ".", "..", ".. \\ \\ ". Daha fazla bilgi için bkz. [PathCommonPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw).

##  <a name="compactpath"></a>CPathT:: CompactPath

Yol bileşenlerini üç noktayla değiştirerek bir dosya yolunu belirli bir piksel genişliğine sığacak şekilde kesmek için bu yöntemi çağırın.

```
BOOL CompactPath(HDC hDC, UINT nWidth);
```

### <a name="parameters"></a>Parametreler

*hDC*<br/>
Yazı tipi ölçümleri için kullanılan cihaz bağlamı.

*nWidth*<br/>
Dizenin sığması için zorlanacak Genişlik (piksel cinsinden).

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathCompactPath](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw).

##  <a name="compactpathex"></a>CPathT:: CompactPathEx

Yol bileşenlerini üç noktayla değiştirerek, bir dosya yolunu belirli sayıda karakter içine sığacak şekilde kesmek için bu yöntemi çağırın.

```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```

### <a name="parameters"></a>Parametreler

*nMaxChars*<br/>
Yeni dizede, Sonlandırıcı NULL karakteri dahil olmak üzere en fazla karakter sayısı.

*dwFlags*<br/>
Ayrılamadı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathCompactPathEx](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw).

##  <a name="cpatht"></a>CPathT:: CPathT

Oluşturucu.

```
CPathT(PCXSTR pszPath);
CPathT(const CPathT<StringType>& path);
CPathT() throw();
```

### <a name="parameters"></a>Parametreler

*pszPath*<br/>
Yol dizesinin işaretçisi.

*Yolun*<br/>
Yol dizesi.

##  <a name="fileexists"></a>CPathT:: FileExists

Bu yol adında dosyanın mevcut olup olmadığını denetlemek için bu yöntemi çağırın.

```
BOOL FileExists() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosya varsa TRUE, aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathFileExists](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw).

##  <a name="findextension"></a>CPathT:: Findexgeri

Yol içinde dosya uzantısının konumunu bulmak için bu yöntemi çağırın.

```
int FindExtension() const;
```

### <a name="return-value"></a>Dönüş Değeri

Uzantısından önceki "." konumunu döndürür. Uzantı bulunamazsa-1 döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Pathfındexgeri](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw).

##  <a name="findfilename"></a>CPathT:: FindFileName

Yolun içindeki dosya adının konumunu bulmak için bu yöntemi çağırın.

```
int FindFileName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosya adının konumunu döndürür. Dosya adı bulunmazsa-1 döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew).

##  <a name="getdrivenumber"></a>CPathT:: GetDriveNumber

' A '-' Z ' aralığı içindeki bir sürücü harfinin yolunu aramak ve karşılık gelen sürücü numarasını döndürmek için bu yöntemi çağırın.

```
int GetDriveNumber() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yolun bir sürücü harfi varsa (' A '-' Z ' öğesine karşılık gelen) 0 ile 25 arasında bir tamsayı olarak sürücü numarasını döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathGetDriveNumber](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw).

##  <a name="getextension"></a>CPathT:: GetExtension

Yoldan dosya uzantısını almak için bu yöntemi çağırın.

```
StringType GetExtension() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosya uzantısını döndürür.

##  <a name="isdirectory"></a>CPathT:: IsDirectory

Yolun geçerli bir dizin olup olmadığını denetlemek için bu yöntemi çağırın.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol bir dizinse sıfır olmayan bir değer döndürür (16), aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Pathisdirectory](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw).

##  <a name="isfilespec"></a>CPathT:: ısdosyabelirtimi

Yol sınırlayan karakterlerin yolunu aramak için bu yöntemi çağırın (örneğin, ': ' veya ' \\ '). Yol sınırlayan karakter yoksa, yol bir dosya belirtimi yolu olarak kabul edilir.

```
BOOL IsFileSpec() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol içinde yol sınırlayan karakterler yoksa TRUE, yol sınırlandırma karakterler varsa FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Pathisdosyabelirtimi](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw).

##  <a name="isprefix"></a>CPathT:: IsPrefix

Bir yolun *pszPrefix*tarafından geçirilen türün geçerli bir önekini içerip içermediğini anlamak için bu yöntemi çağırın.

```
BOOL IsPrefix(PCXSTR pszPrefix) const;
```

### <a name="parameters"></a>Parametreler

*pszPrefix*<br/>
Aranacak ön ek. Ön ek şu türlerden biridir: "C: \\ \\", ".", "..", ".. \\ \\ ".

### <a name="return-value"></a>Dönüş Değeri

Yol öneki içeriyorsa TRUE, aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Pathisprefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw).

##  <a name="isrelative"></a>CPathT:: ısgöreli

Yolun göreli olup olmadığını anlamak için bu yöntemi çağırın.

```
BOOL IsRelative() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol göreli ise TRUE, mutlak ise FALSE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Pathısgöreli](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew).

##  <a name="isroot"></a>CPathT:: IsRoot

Yolun bir dizin kökü olup olmadığını anlamak için bu yöntemi çağırın.

```
BOOL IsRoot() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol bir kök ise TRUE, aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Pathisroot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw).

##  <a name="issameroot"></a>CPathT:: IsSameRoot

Başka bir yolun geçerli yol ile ortak bir kök bileşene sahip olup olmadığını anlamak için bu yöntemi çağırın.

```
BOOL IsSameRoot(PCXSTR pszOther) const;
```

### <a name="parameters"></a>Parametreler

*pszOther*<br/>
Diğer yol.

### <a name="return-value"></a>Dönüş Değeri

Her iki dize de aynı kök bileşene sahip olursa TRUE, aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Pathissameroot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw).

##  <a name="isunc"></a>CPathT:: IsUnc

Yolun bir sunucu ve paylaşma için geçerli bir UNC (evrensel adlandırma kuralı) yolu olup olmadığını öğrenmek için bu yöntemi çağırın.

```
BOOL IsUNC() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol geçerli bir UNC yolu ise TRUE, aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Pathisunc](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw).

##  <a name="isuncserver"></a>CPathT:: ısuncserver

Yolun yalnızca bir sunucu için geçerli bir UNC (evrensel adlandırma kuralı) yolu olup olmadığını öğrenmek için bu yöntemi çağırın.

```
BOOL IsUNCServer() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dize yalnızca sunucu için geçerli bir UNC yolu (paylaşma adı yok) ise TRUE, aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Pathisuncserver](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw).

##  <a name="isuncservershare"></a>CPathT:: ısuncservershare

Yolun geçerli bir UNC (evrensel adlandırma kuralı) paylaşma yolu olup olmadığını (\\ \ *server* \ *paylaşımının*mi olduğunu öğrenmek için bu yöntemi çağırın.

```
BOOL IsUNCServerShare() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol \\ \ *server* \ *paylaşımında*ise true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Pathisuncservershare](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew).

##  <a name="m_strpath"></a>CPathT:: m_strPath

Yol.

```
StringType m_strPath;
```

### <a name="remarks"></a>Açıklamalar

`StringType`, `CPathT` şablon parametresidir.

##  <a name="makepretty"></a>CPathT:: Makeoldukça

Yolun tutarlı bir görünüm sağlamak için bir yolu tüm küçük harfli karakterlere dönüştürmek için bu yöntemi çağırın.

```
BOOL MakePretty();
```

### <a name="return-value"></a>Dönüş Değeri

Yol dönüştürülürse TRUE, aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Pathmakeoldukça](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw).

##  <a name="matchspec"></a>CPathT:: MatchSpec

Joker karakter eşleşme türü içeren bir dizenin yolunu aramak için bu yöntemi çağırın.

```
BOOL MatchSpec(PCXSTR pszSpec) const;
```

### <a name="parameters"></a>Parametreler

*pszSpec*<br/>
Aranacak dosya türüne sahip null ile sonlandırılmış bir dize işaretçisi. Örneğin, geçerli yoldaki dosyanın bir belge dosyası olup olmadığını test etmek için *pszSpec* "*. doc" olarak ayarlanmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Dize eşleşiyorsa TRUE, aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathMatchSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw).

##  <a name="operator_add_eq"></a>CPathT:: operator + =

Bu işleç yola bir dize ekler.

```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```

### <a name="parameters"></a>Parametreler

*pszMore*<br/>
Eklenecek dize.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş yolu döndürür.

##  <a name="operator_const_stringtype_amp"></a>CPathT:: operator const StringType &amp;

Bu işleç nesnenin bir dize gibi işlenmesine izin verir.

```
operator const StringType&() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne tarafından yönetilen geçerli yolu temsil eden bir dize döndürür.

##  <a name="operator_cpatht__pcxstr"></a>CPathT:: operator CPathT::P CXSTR

Bu işleç nesnenin bir dize gibi işlenmesine izin verir.

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne tarafından yönetilen geçerli yolu temsil eden bir dize döndürür.

##  <a name="operator_stringtype_amp"></a>CPathT:: operator StringType &amp;

Bu işleç nesnenin bir dize gibi işlenmesine izin verir.

```
operator StringType&() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne tarafından yönetilen geçerli yolu temsil eden bir dize döndürür.

##  <a name="pcxstr"></a>CPathT::P CXSTR

Sabit bir dize türü.

```
typedef StringType::PCXSTR PCXSTR;
```

### <a name="remarks"></a>Açıklamalar

`StringType`, `CPathT` şablon parametresidir.

##  <a name="pxstr"></a>CPathT::P XSTR

Bir dize türü.

```
typedef StringType::PXSTR PXSTR;
```

### <a name="remarks"></a>Açıklamalar

`StringType`, `CPathT` şablon parametresidir.

##  <a name="quotespaces"></a>CPathT:: QuoteSpaces

Herhangi bir boşluk içeriyorsa, yolu tırnak işaretleri içine almak için bu yöntemi çağırın.

```
void QuoteSpaces();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathQuoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw).

##  <a name="relativepathto"></a>CPathT:: RelativePathTo

Bir dosyadan veya klasörden diğerine göreli yol oluşturmak için bu yöntemi çağırın.

```
BOOL RelativePathTo(
    PCXSTR pszFrom,
    DWORD dwAttrFrom,
    PCXSTR pszTo,
    DWORD dwAttrTo);
```

### <a name="parameters"></a>Parametreler

*pszFrom*<br/>
Göreli yolun başlangıcı.

*dwAttrFrom*<br/>
*PszFrom*dosya öznitelikleri. Bu değer FILE_ATTRIBUTE_DIRECTORY içeriyorsa, *pszFrom* 'un bir dizin olduğu varsayılır; Aksi takdirde, *pszFrom* 'un bir dosya olduğu varsayılır.

*pszTo*<br/>
Göreli yolun bitiş noktası.

*dwAttrTo*<br/>
*PszTo*'nın dosya öznitelikleri. Bu değer FILE_ATTRIBUTE_DIRECTORY içeriyorsa, *pszTo* 'nun bir dizin olduğu varsayılır; Aksi takdirde, *pszTo* 'nın bir dosya olduğu varsayılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow).

##  <a name="removeargs"></a>CPathT:: RemoveArgs

Yoldaki komut satırı bağımsız değişkenlerini kaldırmak için bu yöntemi çağırın.

```
void RemoveArgs();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathRemoveArgs](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw).

##  <a name="removebackslash"></a>CPathT:: Removeters eğik çizgi

Yolun sonundaki ters eğik çizgiyi kaldırmak için bu yöntemi çağırın.

```
void RemoveBackslash();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Pathremoveters eğik çizgi](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw).

##  <a name="removeblanks"></a>CPathT:: Removeboşlar

Yoldan baştaki ve sondaki boşlukları kaldırmak için bu yöntemi çağırın.

```
void RemoveBlanks();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Pathremoveboşlar](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw).

##  <a name="removeextension"></a>CPathT:: RemoveExtension

Dosya uzantısını yoldan kaldırmak için bu yöntemi çağırın.

```
void RemoveExtension();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathRemoveExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw).

##  <a name="removefilespec"></a>CPathT:: Removedosyabelirtimi

Bu yöntemi, varsa sonunda dosya adını ve ters eğik çizgiyi kaldırmak için çağırın.

```
BOOL RemoveFileSpec();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Pathremovedosyabelirtimi](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw).

##  <a name="renameextension"></a>CPathT:: RenameExtension

Yoldaki dosya adı uzantısını yeni bir uzantıyla değiştirmek için bu yöntemi çağırın. Dosya adı bir uzantı içermiyorsa, uzantı yolun sonuna iliştirilir.

```
BOOL RenameExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>Parametreler

*pszExtension*<br/>
Önce bir "." karakteri ile yeni dosya adı uzantısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathRenameExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw).

##  <a name="skiproot"></a>CPathT:: SkipRoot

Sürücü harfi veya UNC (evrensel adlandırma kuralı) sunucu/paylaşma yolu parçalarını yoksayarak bir yolu ayrıştırmak için bu yöntemi çağırın.

```
int SkipRoot() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kökü izleyen alt yolun başlangıcının konumunu döndürür (sürücü harfi veya UNC sunucusu/paylaşma).

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathSkipRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw).

##  <a name="strippath"></a>CPathT:: StripPath

Tam nitelenmiş yolun ve dosya adının yol bölümünü kaldırmak için bu yöntemi çağırın.

```
void StripPath();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathStripPath](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw).

##  <a name="striptoroot"></a>CPathT:: StripToRoot

Kök bilgileri hariç yolun tüm bölümlerini kaldırmak için bu yöntemi çağırın.

```
BOOL StripToRoot();
```

### <a name="return-value"></a>Dönüş Değeri

Yolda geçerli bir sürücü harfi bulunursa TRUE, aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathStripToRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw).

##  <a name="unquotespaces"></a>CPathT:: UnquoteSpaces

Yolun başındaki ve sonundaki tırnak işaretlerini kaldırmak için bu yöntemi çağırın.

```
void UnquoteSpaces();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [PathUnquoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw).

##  <a name="xchar"></a>CPathT:: XCHAR

Bir karakter türü.

```
typedef StringType::XCHAR XCHAR;
```

### <a name="remarks"></a>Açıklamalar

`StringType`, `CPathT` şablon parametresidir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../atl/reference/atl-classes.md)<br/>
[CStringT Sınıfı](../../atl-mfc-shared/reference/cstringt-class.md)
