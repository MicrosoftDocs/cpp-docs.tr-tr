---
title: "MFC uygulamalarında yerelleştirilmiş kaynaklar: Uydu DLL'leri"
ms.date: 11/04/2016
helpviewer_keywords:
- multiple language support [C++]
- localization [C++], MFC resources
- localized resources [C++]
- MFC DLLs [C++], localizing
- DLLs [C++], localizing MFC
- resources [MFC], localizing
- resource-only DLLs [C++]
- resource-only DLLs [C++], MFC applications
- satellite DLLs [C++]
ms.assetid: 3a1100ae-a9c8-47b5-adbd-cbedef5992ef
ms.openlocfilehash: 1f512cc17832564b5eb530b97f8bfb2642c43d43
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220748"
---
# <a name="localized-resources-in-mfc-applications-satellite-dlls"></a>MFC uygulamalarında yerelleştirilmiş kaynaklar: Uydu DLL'leri

MFC sürüm 7.0 ve üzeri, Uydu DLL'leri, çoklu dillerde yerelleşmiş uygulamalar oluşturmaya yardım eden bir özellik için gelişmiş destek sağlar. Bir uydu DLL bir [yalnızca kaynak DLL](creating-a-resource-only-dll.md) uygulama için belirli bir dil için yerelleştirilmiş kaynaklar içerir. Uygulama çalışmaya başladığında, MFC, ortamınız için en uygun yerelleştirilmiş kaynak otomatik olarak yükler. Örneğin, iki Uydu DLL'leri, Fransız bir çeviri kaynaklarınızı ve Almanca çevirisini içeren diğer içeren ile İngilizce dil kaynakları ile bir uygulama olabilir. Uygulamayı bir İngilizce sistemde çalıştırdığınızda, İngilizce kaynak kullanır. Fransız bir sistemde, Fransızca kaynakları kullanır; Almanca bir sistemde, Alman kaynakları kullanır.

Bir MFC uygulamasında, bir uydu DLL yüklemeyi dener yerelleştirilmiş kaynakları desteklemek için kaynakları içeren belirli bir dil için yerelleştirilmiş. Uydu DLL'leri adlı *ApplicationNameXXX*.dll, burada *ApplicationName* .exe veya .dll, MFC kullanarak adıdır ve *XXX* üç harfli dil kodu Kaynakları (örneğin, 'Trk' veya 'DEU').

MFC her biri bulduğunda durdurma sırasıyla aşağıdaki diller için ' % s'kaynak DLL'ini yükler dener:

1. GetUserDefaultUILanguage() Win32 API öğesinden geri döndürülen şekilde geçerli kullanıcının varsayılan kullanıcı Arabirimi dili.

1. Belirli bir alt dili olmadan geçerli kullanıcının varsayılan kullanıcı Arabirimi dilinde (yani ENC [Kanada İngilizce] [ABD trk olur İngilizce]).

1. GetSystemDefaultUILanguage() API'den döndürülen sistemin varsayılan kullanıcı Arabirimi dili. Diğer platformlarda OS dili budur.

1. Sistemin varsayılan kullanıcı Arabirimi dili, belirli bir alt dili olmadan.

1. Loc 3 harfli kod ile sahte bir dil

MFC herhangi bir Uydu DLL'leri bulamazsa, hangi kaynak uygulama içinde yer alan kullanır.

Örneğin, uygulamanın LangExample.exe MFC kullanır ve bir birden çok kullanıcı arabirimi sistemi üzerinde çalışan varsayın. Sistem kullanıcı arabiriminde trk [ABD olan İngilizce] ve [Kanada Fransızcası] FRC için geçerli kullanıcının kullanıcı Arabirimi dilinde ayarlanır. MFC aşağıdaki DLL'leri şu sırayla arar:

1. LangExampleFRC.dll (kullanıcı arabiriminde).

1. LangExampleFRA.dll (kullanıcının kullanıcı Arabirimi dili Fransızca (Fransa) Bu örnekte alt dili olmadan.

1. LangExampleENU.dll (sistem kullanıcı Arabirimi dilinde).

1. LangExampleLOC.dll.

Bu DLL'leri hiçbiri bulunursa, MFC LangExample.exe'deki kaynakları kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da C/C++ DLL'leri oluşturma](dlls-in-visual-cpp.md)<br/>
[TN057: MFC Bileşenlerinin Yerelleştirilmesi](../mfc/tn057-localization-of-mfc-components.md)
