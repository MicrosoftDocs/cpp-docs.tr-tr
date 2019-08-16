---
title: ATL Yardımcı Programları Başvurusu
ms.date: 11/04/2016
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
ms.openlocfilehash: 6c1481929f832e6f810ce46773f328f278b503fa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491710"
---
# <a name="atl-utilities-reference"></a>ATL Yardımcı Programları Başvurusu

ATL, yolları ve URL 'Leri [CPathT](../atl/reference/cpatht-class.md) ve [kıvrımlı](../atl/reference/curl-class.md)biçiminde işlemek için kod sağlar. İş parçacığı havuzu, [CThreadPool](../atl/reference/cthreadpool-class.md), uygulamalarınızda kullanılabilir. Bu kod, atlpath. h ve atlutil. h içinde bulunabilir.

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[CPathT Sınıfı](../atl/reference/cpatht-class.md)|Bu sınıf bir yolu temsil eder.|
|[CDebugReportHook Sınıfı](../atl/reference/cdebugreporthook-class.md)|Bir adlandırılmış kanala hata ayıklama raporları göndermek için bu sınıfı kullanın.|
|[CNonStatelessWorker Sınıfı](../atl/reference/cnonstatelessworker-class.md)|Bir iş parçacığı havuzundan istekleri alır ve her istekte oluşturulan ve yok edilen bir çalışan nesnesine geçirir.|
|[CNoWorkerThread Sınıfı](../atl/reference/cnoworkerthread-class.md)|Dinamik önbellek bakımını devre dışı bırakmak istiyorsanız bu `MonitorClass` sınıfı önbelleğe almak için şablon parametresinin bağımsız değişkeni olarak kullanın.|
|[CThreadPool Sınıfı](../atl/reference/cthreadpool-class.md)|Bu sınıf iş öğelerinin bir kuyruğunu işleyen çalışan iş parçacıklarının havuzunu sağlar.|
|[CUrl Sınıfı](../atl/reference/curl-class.md)|Bu sınıf bir URL 'YI temsil eder. Var olan bir URL dizesi ayrıştırıp veya sıfırdan dize oluşturarak, URL 'nin her bir öğesini diğerlerinden bağımsız olarak değiştirmenize olanak sağlar.|
|[CWorkerThread Sınıfı](../atl/reference/cworkerthread-class.md)|Bu sınıf, bir çalışan iş parçacığı oluşturur veya var olanı kullanır, bir veya daha fazla çekirdek nesne tanıtıcılarını bekler ve tutamaçlardan biri sinyalde olduğunda belirtilen bir istemci işlevini yürütür.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[CPath](../atl/reference/atl-typedefs.md#cpath)|Kullanarak`CString` [CPathT](../atl/reference/cpatht-class.md) özelleştirmesi.|
|[CPathA](../atl/reference/atl-typedefs.md#cpatha)|Kullanarak`CStringA` [CPathT](../atl/reference/cpatht-class.md) özelleştirmesi.|
|[CPathW](../atl/reference/atl-typedefs.md#cpathw)|Kullanarak`CStringW` [CPathT](../atl/reference/cpatht-class.md) özelleştirmesi.|
|[ATL_URL_PORT](../atl/reference/atl-typedefs.md#atl_url_port)|Bir bağlantı noktası numarası belirtmek için [kıvrımlı](../atl/reference/curl-class.md) tarafından kullanılan tür.|

### <a name="enums"></a>Numaralandırmalar

|||
|-|-|
|[ATL_URL_SCHEME](../atl/reference/atl-url-scheme-enum.md)|Bu numaralandırmanın üyeleri, [kıvrımlı](../atl/reference/curl-class.md)tarafından anlaşılan şemalar için sabitler sağlar.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[AtlCanonicalizeUrl](../atl/reference/atl-http-utility-functions.md#atlcanonicalizeurl)|Güvenli olmayan karakterleri ve boşlukları kaçış sıralarına dönüştürme içeren bir URL'yi kurallı hale getirmek için bu işlevi çağırın.|
|[AtlCombineUrl](../atl/reference/atl-http-utility-functions.md#atlcombineurl)|Temel URL ile göreli bir URL'yi, kurallı tek bir URL'de birleştirmek için bu işlevi çağırın.|
|[Attascapeurl 'Si](../atl/reference/atl-http-utility-functions.md#atlescapeurl)|Tüm güvenli olmayan karakterleri kaçış sıralarına dönüştürmek için bu işlevi çağırın.|
|[AtlGetDefaultUrlPort](../atl/reference/atl-http-utility-functions.md#atlgetdefaulturlport)|Belirli bir İnternet protokolüyle veya düzeniyle ilişkili varsayılan bağlantı noktası numarasını almak için bu işlevi çağırın.|
|[Atlonaltıl değeri](../atl/reference/atl-text-encoding-functions.md#atlhexvalue)|Onaltılık basamağın sayısal değerini almak için bu işlevi çağırın.|
|[AtlIsUnsafeUrlChar](../atl/reference/atl-http-utility-functions.md#atlisunsafeurlchar)|Bir karakterin URL'de kullanılmak üzere güvenli olup olmadığını öğrenmek için bu işlevi çağırın.|
|[AtlUnescapeUrl 'Si](../atl/reference/atl-http-utility-functions.md#atlunescapeurl)|Kaçış karakterlerini orijinal değerlerine döndürmek için bu işlevi çağırın.|
|[SystemTimeToHttpDate](../atl/reference/atl-http-utility-functions.md#systemtimetohttpdate)|Sistem saatini HTTP üstbilgileri kullanmak için uygun bir biçimde bir dizeye dönüştürmek için bu işlevi çağırın.|

|[ATLPath::AddBackslash](../atl/reference/atl-path-functions.md#addbackslash)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha
). | |[ ATLPath::AddExtension](../atl/reference/atl-path-functions.md#addextension)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathAddExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw). | |[ ATLPath::Append](../atl/reference/atl-path-functions.md#append)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathAppend](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw). | |[ ATLPath::BuildRoot](../atl/reference/atl-path-functions.md#buildroot)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathBuildRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw). | |[ ATLPath::Canonicalize](../atl/reference/atl-path-functions.md#canonicalize)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew). | |[ ATLPath::Combine](../atl/reference/atl-path-functions.md#combine)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCombine](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew). | |[ ATLPath::CommonPrefix](../atl/reference/atl-path-functions.md#commonprefix)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCommonPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw). | |[ ATLPath::CompactPath](../atl/reference/atl-path-functions.md#compactpath)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCompactPath](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw). | |[ ATLPath::CompactPathEx](../atl/reference/atl-path-functions.md#compactpathex)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathCompactPathEx](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw). | |[ ATLPath::FileExists](../atl/reference/atl-path-functions.md#fileexists)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathFileExists](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw). | |[ ATLPath::FindExtension](../atl/reference/atl-path-functions.md#findextension)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathFindExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw). | |[ ATLPath::FindFileName](../atl/reference/atl-path-functions.md#findfilename)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew). | |[ ATLPath::GetDriveNumber](../atl/reference/atl-path-functions.md#getdrivenumber)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [PathGetDriveNumber](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw). | |[ ATLPath::IsDirectory](../atl/reference/atl-path-functions.md#isdirectory)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısdirectory](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw). | |[ ATLPath::IsFileSpec](../atl/reference/atl-path-functions.md#isfilespec)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısfilespec](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw). | |[ ATLPath::IsPrefix](../atl/reference/atl-path-functions.md#isprefix)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısprefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw). | |[ ATLPath::IsRelative](../atl/reference/atl-path-functions.md#isrelative)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısrelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew). | |[ ATLPath::IsRoot](../atl/reference/atl-path-functions.md#isroot)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısroot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw). | |[ ATLPath::IsSameRoot](../atl/reference/atl-path-functions.md#issameroot)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathıssameroot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw). | |[ ATLPath::IsUNC](../atl/reference/atl-path-functions.md#isunc)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısunc](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw). | |[ ATLPath::IsUNCServer](../atl/reference/atl-path-functions.md#isuncserver)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısuncserver](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw). | |[ ATLPath::IsUNCServerShare](../atl/reference/atl-path-functions.md#isuncservershare)| Bu işlev için aşırı yüklenmiş bir sarmalayıcıdır, [Pathısuncservershare](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew).| |[ATLPath::MakePretty](../atl/reference/atl-path-functions.md#makepretty)|This function is an overloaded wrapper for [PathMakePretty](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw).| |[ATLPath::MatchSpec](../atl/reference/atl-path-functions.md#matchspec)|This function is an overloaded wrapper for [PathMatchSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw).| |[ATLPath::QuoteSpaces](../atl/reference/atl-path-functions.md#quotespaces)|This function is an overloaded wrapper for [PathQuoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw).| |[ATLPath::RelativePathTo](../atl/reference/atl-path-functions.md#relativepathto)|This function is an overloaded wrapper for [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow).| |[ATLPath::RemoveArgs](../atl/reference/atl-path-functions.md#removeargs)|This function is an overloaded wrapper for [PathRemoveArgs](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw).| |[ATLPath::RemoveBackslash](../atl/reference/atl-path-functions.md#removebackslash)|This function is an overloaded wrapper for [PathRemoveBackslash](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw).| |[ATLPath::RemoveBlanks](../atl/reference/atl-path-functions.md#removeblanks)|This function is an overloaded wrapper for [PathRemoveBlanks](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw).| |[ATLPath::RemoveExtension](../atl/reference/atl-path-functions.md#removeextension)|This function is an overloaded wrapper for [PathRemoveExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw).| |[ATLPath::RemoveFileSpec](../atl/reference/atl-path-functions.md#removefilespec)|This function is an overloaded wrapper for [PathRemoveFileSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw).| |[ATLPath::RenameExtension](../atl/reference/atl-path-functions.md#renameextension)|This function is an overloaded wrapper for [PathRenameExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw).| |[ATLPath::SkipRoot](../atl/reference/atl-path-functions.md#skiproot)|This function is an overloaded wrapper for [PathSkipRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw).| |[ATLPath::StripPath](../atl/reference/atl-path-functions.md#strippath)|This function is an overloaded wrapper for [PathStripPath](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw).| |[ATLPath::StripToRoot](../atl/reference/atl-path-functions.md#striptoroot)|This function is an overloaded wrapper for [PathStripToRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw).| |[ATLPath::UnquoteSpaces](../atl/reference/atl-path-functions.md#unquotespaces)|This function is an overloaded wrapper for [PathUnquoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw).|

## <a name="see-also"></a>Ayrıca bkz.

[Tiren](../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM Masaüstü Bileşenleri](../atl/atl-com-desktop-components.md)
