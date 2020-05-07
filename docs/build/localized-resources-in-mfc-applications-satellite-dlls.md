---
title: "MFC Uygulamalarında Yerelleştirilmiş Kaynaklar: Uydu DLL'leri"
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
# <a name="localized-resources-in-mfc-applications-satellite-dlls"></a>MFC Uygulamalarında Yerelleştirilmiş Kaynaklar: Uydu DLL'leri

MFC sürüm 7,0 ve üzeri, birden çok dil için yerelleştirilmiş uygulamalar oluşturmaya yardımcı olan bir özellik olan uydu dll 'Leri için gelişmiş destek sağlar. Uydu DLL 'si, belirli bir dil için yerelleştirilmiş bir uygulama kaynaklarını içeren [yalnızca kaynak dll](creating-a-resource-only-dll.md) 'dir. Uygulama yürütülmeye başladığında, MFC ortamı için en uygun yerelleştirilmiş kaynağı otomatik olarak yükler. Örneğin, biri kaynaklarınızın Fransızca çevirisini içeren, diğeri de Almanya çevirisi içeren, iki uydu dll içeren Ingilizce dil kaynakları içeren bir uygulamanıza sahip olabilirsiniz. Uygulama Ingilizce bir dil sisteminde çalıştırıldığında, Ingilizce kaynakları kullanır. Bir Fransızca sistemde çalışıyorsa, Fransızca kaynaklarını kullanır; Almanya sisteminde çalıştırırsanız, Almanya kaynaklarını kullanır.

MFC uygulamasındaki yerelleştirilmiş kaynakları desteklemek için, MFC belirli bir dile yerelleştirilmiş kaynakları içeren bir uydu DLL yüklemeye çalışır. Uydu dll 'Leri, *uygulama*adı. exe veya. dll *' nin MFC* kullanılarak adıdır ve *XXX* , kaynakların dili için üç harflı koddur (örneğin, ' trk ' veya ' DEU ').

MFC, her bir aşağıdaki dilin kaynak DLL 'sini sırayla yüklemeye çalışır, bir tane bulduğunda durdurulur:

1. Geçerli kullanıcının varsayılan kullanıcı arabirimi dili, GetUserDefaultUILanguage () Win32 API döndürüldü.

1. Geçerli kullanıcının varsayılan kullanıcı arabirimi dili, belirli bir alt dil olmadan (yani ENC [Kanada Ingilizce], trk [ABD Ingilizcesi] olur).

1. Sistemin, GetSystemDefaultUILanguage () API 'sinden döndürülen varsayılan kullanıcı arabirimi dili. Diğer platformlarda bu, işletim sisteminin kendisi dilidir.

1. Sistemin varsayılan kullanıcı arabirimi dili, belirli bir alt dil olmadan.

1. 3 harfli kod LOC ile sahte bir dil.

MFC herhangi bir uydu dll bulamazsa, uygulamanın kendisine dahil edilen kaynakları kullanır.

Örnek olarak, bir Application LangExample. exe ' nin MFC kullandığını ve birden çok kullanıcı arabirimi sisteminde çalıştığını varsayalım; Sistem kullanıcı arabirimi dili trk [ABD Ingilizcesi] ve geçerli kullanıcının kullanıcı ARABIRIMI dili FRC [Kanada Fransızcası] olarak ayarlanmıştır. MFC, aşağıdaki dll 'Leri aşağıdaki sırayla arar:

1. LangExampleFRC. dll (kullanıcının kullanıcı ARABIRIMI dili).

1. LangExampleFRA. dll (kullanıcının kullanıcı ARABIRIMI dili alt dil olmadan, bu örnekte Fransızca (Fransa).

1. Langexampletrk. dll (sistemin Kullanıcı arabirimi dili).

1. LangExampleLOC. dll.

Bu dll 'Lerden hiçbiri bulunamazsa, MFC LangExample. exe dosyasındaki kaynakları kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C/C++ dll 'Leri oluşturma](dlls-in-visual-cpp.md)<br/>
[TN057: MFC Bileşenlerini Yerelleştirme](../mfc/tn057-localization-of-mfc-components.md)
