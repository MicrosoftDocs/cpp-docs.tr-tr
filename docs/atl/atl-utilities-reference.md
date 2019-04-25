---
title: ATL Yardımcı Programları Başvurusu
ms.date: 11/04/2016
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
ms.openlocfilehash: b5365ddc2924955fbdcf694065c4d4041a38eb01
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62251869"
---
# <a name="atl-utilities-reference"></a>ATL Yardımcı Programları Başvurusu

ATL yollarını ve URL'leri biçiminde işlemek için kod sağlar [CPathT](../atl/reference/cpatht-class.md) ve [CUrl](../atl/reference/curl-class.md). İş parçacığı havuzu [CThreadPool](../atl/reference/cthreadpool-class.md), uygulamalarınızda kullanılabilir. Bu kod, atlpath.h ve atlutil.h bulunabilir.

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[CPathT Sınıfı](../atl/reference/cpatht-class.md)|Bu sınıf, bir yol gösterir.|
|[CDebugReportHook Sınıfı](../atl/reference/cdebugreporthook-class.md)|Bu sınıf, hata ayıklama raporları bir adlandırılmış kanala göndermek için kullanın.|
|[CNonStatelessWorker Sınıfı](../atl/reference/cnonstatelessworker-class.md)|Bir iş parçacığı havuzundan isteklerini alır ve bunları her istekte oluşturulur ve imha bir alt nesnesi açın geçirir.|
|[CNoWorkerThread Sınıfı](../atl/reference/cnoworkerthread-class.md)|Bu sınıf için bağımsız değişken olarak kullanmak `MonitorClass` şablon parametresi için dinamik önbellek bakım devre dışı bırakmak isterseniz önbellek sınıfları.|
|[CThreadPool Sınıfı](../atl/reference/cthreadpool-class.md)|Bu sınıf, iş öğelerinin bir kuyruğu işleyen çalışan iş parçacığı havuzu sağlar.|
|[CUrl Sınıfı](../atl/reference/curl-class.md)|Bu sınıf, bir URL temsil eder. Var olan bir URL Ayrıştırma olup olmadığını her öğeyi diğerlerinden URL'sinin düzenlemesini sağlar dize veya bir dize sıfırdan oluşturma.|
|[CWorkerThread Sınıfı](../atl/reference/cworkerthread-class.md)|Bu sınıf bir çalışan iş parçacığı oluşturur veya mevcut bir kullanır, bir veya daha fazla çekirdek nesne tutamaçları bekler ve tutamaçlarından birinin sinyal, belirtilen istemci işlevi yürütür.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[CPath](../atl/reference/atl-typedefs.md#cpath)|Bir alt uzmanlaşması [CPathT](../atl/reference/cpatht-class.md) kullanarak `CString`.|
|[CPathA](../atl/reference/atl-typedefs.md#cpatha)|Bir alt uzmanlaşması [CPathT](../atl/reference/cpatht-class.md) kullanarak `CStringA`.|
|[CPathW](../atl/reference/atl-typedefs.md#cpathw)|Bir alt uzmanlaşması [CPathT](../atl/reference/cpatht-class.md) kullanarak `CStringW`.|
|[ATL_URL_PORT](../atl/reference/atl-typedefs.md#atl_url_port)|Tarafından kullanılan türü [CUrl](../atl/reference/curl-class.md) bir bağlantı noktası numarası belirtmek için.|

### <a name="enums"></a>Numaralandırmalar

|||
|-|-|
|[ATL_URL_SCHEME](../atl/reference/atl-url-scheme-enum.md)|Bu numaralandırma üyeleri tarafından anlaşılan düzenleri için sabitleri sağlayan [CUrl](../atl/reference/curl-class.md).|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[AtlCanonicalizeUrl](../atl/reference/atl-http-utility-functions.md#atlcanonicalizeurl)|Güvenli olmayan karakterleri ve boşlukları kaçış sıralarına dönüştürme içeren bir URL'yi kurallı hale getirmek için bu işlevi çağırın.|
|[AtlCombineUrl](../atl/reference/atl-http-utility-functions.md#atlcombineurl)|Temel URL ile göreli bir URL'yi, kurallı tek bir URL'de birleştirmek için bu işlevi çağırın.|
|[AtlEscapeUrl](../atl/reference/atl-http-utility-functions.md#atlescapeurl)|Tüm güvenli olmayan karakterleri kaçış sıralarına dönüştürmek için bu işlevi çağırın.|
|[AtlGetDefaultUrlPort](../atl/reference/atl-http-utility-functions.md#atlgetdefaulturlport)|Belirli bir internet protokolü veya düzeni ile ilişkili varsayılan bağlantı noktası numarasını almak için bu işlevi çağırın.|
|[AtlHexValue](../atl/reference/atl-text-encoding-functions.md#atlhexvalue)|Onaltılık basamağın sayısal değerini almak için bu işlevi çağırın.|
|[AtlIsUnsafeUrlChar](../atl/reference/atl-http-utility-functions.md#atlisunsafeurlchar)|Bir karakterin URL'de kullanılmak üzere güvenli olup olmadığını öğrenmek için bu işlevi çağırın.|
|[AtlUnescapeUrl](../atl/reference/atl-http-utility-functions.md#atlunescapeurl)|Kaçış karakterlerini orijinal değerlerine döndürmek için bu işlevi çağırın.|
|[SystemTimeToHttpDate](../atl/reference/atl-http-utility-functions.md#systemtimetohttpdate)|Sistem saatini HTTP üstbilgileri kullanmak için uygun bir biçimde bir dizeye dönüştürmek için bu işlevi çağırın.|

|[ATLPath::AddBackslash](../atl/reference/atl-path-functions.md#addbackslash)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha
). | |[ ATLPath::AddExtension](../atl/reference/atl-path-functions.md#addextension)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona). | |[ ATLPath::Append](../atl/reference/atl-path-functions.md#append)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda). | |[ ATLPath::BuildRoot](../atl/reference/atl-path-functions.md#buildroot)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota). | |[ ATLPath::Canonicalize](../atl/reference/atl-path-functions.md#canonicalize)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea). | |[ ATLPath::Combine](../atl/reference/atl-path-functions.md#combine)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea). | |[ ATLPath::CommonPrefix](../atl/reference/atl-path-functions.md#commonprefix)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa). | |[ ATLPath::CompactPath](../atl/reference/atl-path-functions.md#compactpath)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha). | |[ ATLPath::CompactPathEx](../atl/reference/atl-path-functions.md#compactpathex)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa). | |[ ATLPath::FileExists](../atl/reference/atl-path-functions.md#fileexists)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa). | |[ ATLPath::FindExtension](../atl/reference/atl-path-functions.md#findextension)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona). | |[ ATLPath::FindFileName](../atl/reference/atl-path-functions.md#findfilename)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea). | |[ ATLPath::GetDriveNumber](../atl/reference/atl-path-functions.md#getdrivenumber)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera). | |[ ATLPath::IsDirectory](../atl/reference/atl-path-functions.md#isdirectory)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısdirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya). | |[ ATLPath::IsFileSpec](../atl/reference/atl-path-functions.md#isfilespec)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısfilespec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca). | |[ ATLPath::IsPrefix](../atl/reference/atl-path-functions.md#isprefix)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısprefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa). | |[ ATLPath::IsRelative](../atl/reference/atl-path-functions.md#isrelative)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısrelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea). | |[ ATLPath::IsRoot](../atl/reference/atl-path-functions.md#isroot)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısroot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota). | |[ ATLPath::IsSameRoot](../atl/reference/atl-path-functions.md#issameroot)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathıssameroot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota). | |[ ATLPath::IsUNC](../atl/reference/atl-path-functions.md#isunc)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısunc](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca). | |[ ATLPath::IsUNCServer](../atl/reference/atl-path-functions.md#isuncserver)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısuncserver](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera). | |[ ATLPath::IsUNCServerShare](../atl/reference/atl-path-functions.md#isuncservershare)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısuncservershare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea).| |[ATLPath::MakePretty](../atl/reference/atl-path-functions.md#makepretty)|This function is an overloaded wrapper for [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya).| |[ATLPath::MatchSpec](../atl/reference/atl-path-functions.md#matchspec)|This function is an overloaded wrapper for [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca).| |[ATLPath::QuoteSpaces](../atl/reference/atl-path-functions.md#quotespaces)|This function is an overloaded wrapper for [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa).| |[ATLPath::RelativePathTo](../atl/reference/atl-path-functions.md#relativepathto)|This function is an overloaded wrapper for [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa).| |[ATLPath::RemoveArgs](../atl/reference/atl-path-functions.md#removeargs)|This function is an overloaded wrapper for [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa).| |[ATLPath::RemoveBackslash](../atl/reference/atl-path-functions.md#removebackslash)|This function is an overloaded wrapper for [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha).| |[ATLPath::RemoveBlanks](../atl/reference/atl-path-functions.md#removeblanks)|This function is an overloaded wrapper for [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa).| |[ATLPath::RemoveExtension](../atl/reference/atl-path-functions.md#removeextension)|This function is an overloaded wrapper for [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona).| |[ATLPath::RemoveFileSpec](../atl/reference/atl-path-functions.md#removefilespec)|This function is an overloaded wrapper for [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca).| |[ATLPath::RenameExtension](../atl/reference/atl-path-functions.md#renameextension)|This function is an overloaded wrapper for [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona).| |[ATLPath::SkipRoot](../atl/reference/atl-path-functions.md#skiproot)|This function is an overloaded wrapper for [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota).| |[ATLPath::StripPath](../atl/reference/atl-path-functions.md#strippath)|This function is an overloaded wrapper for [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha).| |[ATLPath::StripToRoot](../atl/reference/atl-path-functions.md#striptoroot)|This function is an overloaded wrapper for [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota).| |[ATLPath::UnquoteSpaces](../atl/reference/atl-path-functions.md#unquotespaces)|This function is an overloaded wrapper for [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa).|

## <a name="see-also"></a>Ayrıca bkz.

[Kavramları](../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM Masaüstü Bileşenleri](../atl/atl-com-desktop-components.md)
