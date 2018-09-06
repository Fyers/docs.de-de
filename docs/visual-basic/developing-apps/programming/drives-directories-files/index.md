---
title: Verarbeiten von Laufwerken, Verzeichnissen und Dateien (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- drives
- drives, processing
- Visual Basic code, file access
- files [Visual Basic], processing
- files [Visual Basic], accessing
- directories [Visual Studio], processing
ms.assetid: f1db14c8-a4fd-4d0b-8323-c7cb29d688c2
ms.openlocfilehash: 0c9c1c787138595f725316a580acda9c5d4d43a9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43662670"
---
# <a name="processing-drives-directories-and-files-visual-basic"></a><span data-ttu-id="26181-102">Verarbeiten von Laufwerken, Verzeichnissen und Dateien (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26181-102">Processing Drives, Directories, and Files (Visual Basic)</span></span>
<span data-ttu-id="26181-103">Sie können Visual Basic zum Verarbeiten von Laufwerken, Ordnern und Dateien mit dem `My.Computer.FileSystem`-Objekt verwenden, das eine bessere Leistung bietet und einfacher zu verwenden ist als herkömmliche Methoden, wie z.B. die `FileOpen`- und `Write`-Funktionen (obwohl sie immer noch verfügbar sind).</span><span class="sxs-lookup"><span data-stu-id="26181-103">You can use Visual Basic to process drives, folders, and files with the `My.Computer.FileSystem` object, which provides better performance and is easier to use than traditional methods such as the `FileOpen` and `Write` functions (although they are still available).</span></span> <span data-ttu-id="26181-104">In den folgenden Abschnitten werden diese Methoden ausführlich erörtert.</span><span class="sxs-lookup"><span data-stu-id="26181-104">The following sections discuss these methods in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="26181-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="26181-105">In This Section</span></span>  
 [<span data-ttu-id="26181-106">Dateizugriff mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26181-106">File Access with Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)  
 <span data-ttu-id="26181-107">Erläutert, wie das `My.Computer.FileSystem`-Objekt verwendet wird, um mit Dateien, Laufwerken und Ordnern zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="26181-107">Discusses how to use the `My.Computer.FileSystem` object to work with files, drives, and folders.</span></span>  
  
 [<span data-ttu-id="26181-108">Grundlagen zu Datei-E/A-Vorgängen und dem Dateisystem in .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26181-108">Basics of .NET Framework File I/O and the File System (Visual Basic)</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)  
 <span data-ttu-id="26181-109">Bietet einen Überblick über die Datei-A/A-Konzepte in .NET Framework, einschließlich Streams, isolierter Speicher, Dateiereignissen, Dateiattributen und Dateizugriff.</span><span class="sxs-lookup"><span data-stu-id="26181-109">Provides an overview of file I/O concepts in the .NET Framework, including streams, isolated storage, file events, file attributes, and file access.</span></span>  
  
 [<span data-ttu-id="26181-110">Exemplarische Vorgehensweise: Bearbeiten von Dateien mit .NET Framework-Methoden</span><span class="sxs-lookup"><span data-stu-id="26181-110">Walkthrough: Manipulating Files by Using .NET Framework Methods</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)  
 <span data-ttu-id="26181-111">Veranschaulicht, wie [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] zum Bearbeiten von Dateien und Ordnern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="26181-111">Demonstrates how to use the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] to manipulate files and folders.</span></span>  
  
 [<span data-ttu-id="26181-112">Exemplarische Vorgehensweise: Bearbeiten von Dateien und Verzeichnissen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26181-112">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)  
 <span data-ttu-id="26181-113">Veranschaulicht, wie das `My.Computer.FileSystem`-Objekt zum Bearbeiten von Dateien und Ordnern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="26181-113">Demonstrates how to use the `My.Computer.FileSystem` object to manipulate files and folders.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="26181-114">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="26181-114">Related Sections</span></span>  
 [<span data-ttu-id="26181-115">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="26181-115">Program Structure and Code Conventions</span></span>](../../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 <span data-ttu-id="26181-116">Enthält Richtlinien für die physische Struktur und die Darstellung von Programmen.</span><span class="sxs-lookup"><span data-stu-id="26181-116">Provides guidelines for the physical structure and appearance of programs.</span></span>  
  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <span data-ttu-id="26181-117">Referenzdokumentation für das `My.Computer.FileSystem`-Objekt und seiner Member.</span><span class="sxs-lookup"><span data-stu-id="26181-117">Reference documentation for the `My.Computer.FileSystem` object and its members.</span></span>