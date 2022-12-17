+++ 
draft = false
date = 2022-12-17T16:15:04+02:00
title = "Antras puslapis"
description = ""
slug = ""
authors = []
tags = []
categories = []
externalLink = ""
series = []
+++
![Paveikslelis](/car.jpg)
{{< highlight go "linenos=table,hl_lines=8 15-17,linenostart=199" >}}
 public static void executeQuery(String query) {
        try {
            dbConnect();
            PreparedStatement psInsert = connection.prepareStatement(query);
            System.out.println(psInsert);
            psInsert.executeUpdate();
            psInsert.close();
        } catch (SQLException e) {
            System.out.println("DB error!\nStatement: " + query); //LOG
            e.printStackTrace();
        } finally {
            try {
                dbDisconnect();
            } catch (SQLException e) {
                e.printStackTrace();
            }
        }
    }
{{< / highlight >}}