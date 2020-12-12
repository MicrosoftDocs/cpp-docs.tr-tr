---
description: 'Daha fazla bilgi edinin: ATL yardımcı programları başvurusu'
title: ATL yardımcı programları başvurusu
ms.date: 11/04/2016
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
ms.openlocfilehash: 8545881c5cd48aaff1bb25448ba443829128dc41
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148583"
---
# <a name="atl-utilities-reference"></a>ATL yardımcı programları başvurusu

ATL, yolları ve URL 'Leri [CPathT](../atl/reference/cpatht-class.md) ve [kıvrımlı](../atl/reference/curl-class.md)biçiminde işlemek için kod sağlar. İş parçacığı havuzu, [CThreadPool](../atl/reference/cthreadpool-class.md), uygulamalarınızda kullanılabilir. Bu kod, atlpath. h ve atlutil. h içinde bulunabilir.

## <a name="classes"></a>Sınıflar

| &nbsp; | &nbsp; |
|--|--|
| [CPathT sınıfı](../atl/reference/cpatht-class.md) | Bu sınıf bir yolu temsil eder. |
| [CDebugReportHook sınıfı](../atl/reference/cdebugreporthook-class.md) | Bir adlandırılmış kanala hata ayıklama raporları göndermek için bu sınıfı kullanın. |
| [CNonStatelessWorker sınıfı](../atl/reference/cnonstatelessworker-class.md) | Bir iş parçacığı havuzundan istekleri alır ve her istekte oluşturulan ve yok edilen bir çalışan nesnesine geçirir. |
| [CNoWorkerThread sınıfı](../atl/reference/cnoworkerthread-class.md) | `MonitorClass`Dinamik önbellek bakımını devre dışı bırakmak istiyorsanız bu sınıfı önbelleğe almak için şablon parametresinin bağımsız değişkeni olarak kullanın. |
| [CThreadPool sınıfı](../atl/reference/cthreadpool-class.md) | Bu sınıf iş öğelerinin bir kuyruğunu işleyen çalışan iş parçacıklarının havuzunu sağlar. |
| [CUrl sınıfı](../atl/reference/curl-class.md) | Bu sınıf bir URL 'YI temsil eder. Var olan bir URL dizesi ayrıştırıp veya sıfırdan dize oluşturarak, URL 'nin her bir öğesini diğerlerinden bağımsız olarak değiştirmenize olanak sağlar. |
| [CWorkerThread sınıfı](../atl/reference/cworkerthread-class.md) | Bu sınıf, bir çalışan iş parçacığı oluşturur veya var olanı kullanır, bir veya daha fazla çekirdek nesne tanıtıcılarını bekler ve tutamaçlardan biri sinyalde olduğunda belirtilen bir istemci işlevini yürütür. |

## <a name="typedefs"></a>Tür tanımları

| &emsp; | &emsp; |
|--|--|
| [CPath](../atl/reference/atl-typedefs.md#cpath) | Kullanarak [CPathT](../atl/reference/cpatht-class.md) özelleştirmesi `CString` . |
| [CPathA](../atl/reference/atl-typedefs.md#cpatha) | Kullanarak [CPathT](../atl/reference/cpatht-class.md) özelleştirmesi `CStringA` . |
| [CPathW](../atl/reference/atl-typedefs.md#cpathw) | Kullanarak [CPathT](../atl/reference/cpatht-class.md) özelleştirmesi `CStringW` . |
| [ATL_URL_PORT](../atl/reference/atl-typedefs.md#atl_url_port) | Bir bağlantı noktası numarası belirtmek için [kıvrımlı](../atl/reference/curl-class.md) tarafından kullanılan tür. |

## <a name="enums"></a>Numaralandırmalar

| &emsp; | &emsp; |
|--|--|
| [ATL_URL_SCHEME](../atl/reference/atl-url-scheme-enum.md) | Bu numaralandırmanın üyeleri, [kıvrımlı](../atl/reference/curl-class.md)tarafından anlaşılan şemalar için sabitler sağlar. |

## <a name="functions"></a>İşlevler

| &emsp; | &emsp; |
|--|--|
| [AtlCanonicalizeUrl](../atl/reference/atl-http-utility-functions.md#atlcanonicalizeurl) | Güvenli olmayan karakterleri ve boşlukları kaçış sıralarına dönüştürme içeren bir URL'yi kurallı hale getirmek için bu işlevi çağırın. |
| [AtlCombineUrl](../atl/reference/atl-http-utility-functions.md#atlcombineurl) | Temel URL ile göreli bir URL'yi, kurallı tek bir URL'de birleştirmek için bu işlevi çağırın. |
| [Attascapeurl 'Si](../atl/reference/atl-http-utility-functions.md#atlescapeurl) | Tüm güvenli olmayan karakterleri kaçış sıralarına dönüştürmek için bu işlevi çağırın. |
| [AtlGetDefaultUrlPort](../atl/reference/atl-http-utility-functions.md#atlgetdefaulturlport) | Belirli bir İnternet protokolüyle veya düzeniyle ilişkili varsayılan bağlantı noktası numarasını almak için bu işlevi çağırın. |
| [Atlonaltıl değeri](../atl/reference/atl-text-encoding-functions.md#atlhexvalue) | Onaltılık basamağın sayısal değerini almak için bu işlevi çağırın. |
| [AtlIsUnsafeUrlChar](../atl/reference/atl-http-utility-functions.md#atlisunsafeurlchar) | Bir karakterin URL'de kullanılmak üzere güvenli olup olmadığını öğrenmek için bu işlevi çağırın. |
| [AtlUnescapeUrl 'Si](../atl/reference/atl-http-utility-functions.md#atlunescapeurl) | Kaçış karakterlerini orijinal değerlerine döndürmek için bu işlevi çağırın. |
| [SystemTimeToHttpDate](../atl/reference/atl-http-utility-functions.md#systemtimetohttpdate) | Sistem saatini HTTP üstbilgileri kullanmak için uygun bir biçimde bir dizeye dönüştürmek için bu işlevi çağırın. |
| [ATLPath:: Addters eğik çizgi](../atl/reference/atl-path-functions.md#addbackslash) | Bu işlev [Pathaddters eğik çizgi] için aşırı yüklenmiş bir sarmalayıcıdır (/Windows/Desktop/api/shlwapi/NF-shlwapi-pathaddbackslasha |
| ). |
| [ATLPath:: Addexgeri](../atl/reference/atl-path-functions.md#addextension) | Bu işlev [Pathaddexgeri](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: Append](../atl/reference/atl-path-functions.md#append) | Bu işlev, [PathAppend](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: BuildRoot](../atl/reference/atl-path-functions.md#buildroot) | Bu işlev, [PathBuildRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: canonicalize](../atl/reference/atl-path-functions.md#canonicalize) | Bu işlev, [PathCanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: birleştirin](../atl/reference/atl-path-functions.md#combine) | Bu işlev, [Pathbirleştirme](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: CommonPrefix](../atl/reference/atl-path-functions.md#commonprefix) | Bu işlev, [PathCommonPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: CompactPath](../atl/reference/atl-path-functions.md#compactpath) | Bu işlev, [PathCompactPath](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: CompactPathEx](../atl/reference/atl-path-functions.md#compactpathex) | Bu işlev, [PathCompactPathEx](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: FileExists](../atl/reference/atl-path-functions.md#fileexists) | Bu işlev, [PathFileExists](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: Findexgeri](../atl/reference/atl-path-functions.md#findextension) | Bu işlev, [Pathfindexgeri](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: FindFileName](../atl/reference/atl-path-functions.md#findfilename) | Bu işlev, [PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: GetDriveNumber](../atl/reference/atl-path-functions.md#getdrivenumber) | Bu işlev, [PathGetDriveNumber](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: IsDirectory](../atl/reference/atl-path-functions.md#isdirectory) | Bu işlev [Pathisdirectory](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: ısdosyabelirtimi](../atl/reference/atl-path-functions.md#isfilespec) | Bu işlev [Pathisdosyabelirtimi](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: Isprefıx](../atl/reference/atl-path-functions.md#isprefix) | Bu işlev [Pathisprefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: ısgöreli](../atl/reference/atl-path-functions.md#isrelative) | Bu işlev, [Pathısgöreli](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: IsRoot](../atl/reference/atl-path-functions.md#isroot) | Bu işlev, [Pathisroot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: IsSameRoot](../atl/reference/atl-path-functions.md#issameroot) | Bu işlev [Pathissameroot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: IsUnc](../atl/reference/atl-path-functions.md#isunc) | Bu işlev [Pathisunc](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: ısuncserver](../atl/reference/atl-path-functions.md#isuncserver) | Bu işlev [Pathisuncserver](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: ısuncservershare](../atl/reference/atl-path-functions.md#isuncservershare) | Bu işlev [Pathisuncservershare](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: Makeoldukça](../atl/reference/atl-path-functions.md#makepretty) | Bu işlev, [Pathmakeoldukça](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: MatchSpec](../atl/reference/atl-path-functions.md#matchspec) | Bu işlev, [PathMatchSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: QuoteSpaces](../atl/reference/atl-path-functions.md#quotespaces) | Bu işlev, [PathQuoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: RelativePathTo](../atl/reference/atl-path-functions.md#relativepathto) | Bu işlev [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: RemoveArgs](../atl/reference/atl-path-functions.md#removeargs) | Bu işlev [PathRemoveArgs](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: Removeters eğik çizgi](../atl/reference/atl-path-functions.md#removebackslash) | Bu işlev [Pathremoveters eğik çizgi](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: Removeboşlar](../atl/reference/atl-path-functions.md#removeblanks) | Bu işlev, [Pathremoveboşluklar](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: RemoveExtension](../atl/reference/atl-path-functions.md#removeextension) | Bu işlev [PathRemoveExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: Removedosyabelirtimi](../atl/reference/atl-path-functions.md#removefilespec) | Bu işlev, [Pathremovedosyabelirtimi](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: RenameExtension](../atl/reference/atl-path-functions.md#renameextension) | Bu işlev [PathRenameExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: SkipRoot](../atl/reference/atl-path-functions.md#skiproot) | Bu işlev [PathSkipRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: StripPath](../atl/reference/atl-path-functions.md#strippath) | Bu işlev, [PathStripPath](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: StripToRoot](../atl/reference/atl-path-functions.md#striptoroot) | Bu işlev, [PathStripToRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)için aşırı yüklenmiş bir sarmalayıcıdır. |
| [ATLPath:: UnquoteSpaces](../atl/reference/atl-path-functions.md#unquotespaces) | Bu işlev, [PathUnquoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)için aşırı yüklenmiş bir sarmalayıcıdır. |

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM Masaüstü bileşenleri](../atl/atl-com-desktop-components.md)
