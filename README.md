package com.gmail.lylecproductions.multisoup;

import org.bukkit.Bukkit;
import org.bukkit.Material;

import org.bukkit.Server;
import org.bukkit.entity.Player;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.event.block.Action;
import org.bukkit.event.player.PlayerInteractEvent;
import org.bukkit.inventory.ItemStack;
import org.bukkit.inventory.ShapelessRecipe;
import org.bukkit.inventory.meta.ItemMeta;
import org.bukkit.plugin.PluginManager;
import org.bukkit.plugin.java.JavaPlugin;

public class Multisoup extends JavaPlugin implements Listener{
  
    @Override
    public void onEnable(){
        PluginManager pm = Bukkit.getPluginManager();
        pm.registerEvents(this, this);
       Server server = this.getServer();
       
       ItemStack cactusStack = new ItemStack(Material.MUSHROOM_SOUP);
       ItemMeta cactusMeta = cactusStack.getItemMeta();
       cactusMeta.setDisplayName("Cacti Juice");
       cactusStack.setItemMeta(cactusMeta);
       ShapelessRecipe cactus = new ShapelessRecipe(cactusStack);
       cactus.addIngredient(2, Material.CACTUS);
       cactus.addIngredient(1, Material.BOWL);
        
       server.addRecipe(cactus);
       
       ItemStack AppleStack = new ItemStack(Material.MUSHROOM_SOUP);
       ItemMeta AppleMeta = AppleStack.getItemMeta();
       AppleMeta.setDisplayName("Apple Juice");
       AppleStack.setItemMeta(AppleMeta);
       ShapelessRecipe apple = new ShapelessRecipe(AppleStack);
       apple.addIngredient(1, Material.APPLE);
       apple.addIngredient(1, Material.BOWL);
    
       server.addRecipe(apple);
       
       ItemStack saplingStack = new ItemStack(Material.MUSHROOM_SOUP);
       ItemMeta saplingMeta = saplingStack.getItemMeta();
       saplingMeta.setDisplayName("Sap Stew");
       saplingStack.setItemMeta(saplingMeta);
       ShapelessRecipe sapling = new ShapelessRecipe(saplingStack);
       sapling.addIngredient(1, Material.SAPLING, 1);
       sapling.addIngredient(1, Material.BOWL);
       
       server.addRecipe(sapling);
       
       ItemStack saplingsStack = new ItemStack(Material.MUSHROOM_SOUP);
       ItemMeta saplingsMeta = saplingsStack.getItemMeta();
       saplingsMeta.setDisplayName("Sap Stew");
       saplingsStack.setItemMeta(saplingsMeta);
       ShapelessRecipe saplings = new ShapelessRecipe(saplingsStack);
       saplings.addIngredient(1, Material.SAPLING, 2);
       saplings.addIngredient(1, Material.BOWL);
       
       server.addRecipe(saplings);
       
       ItemStack saplings1Stack = new ItemStack(Material.MUSHROOM_SOUP);
       ItemMeta saplings1Meta = saplings1Stack.getItemMeta();
       saplings1Meta.setDisplayName("Sap Stew");
       saplings1Stack.setItemMeta(saplings1Meta);
       ShapelessRecipe saplings1 = new ShapelessRecipe(saplings1Stack);
       saplings1.addIngredient(1, Material.SAPLING, 3);
       saplings1.addIngredient(1, Material.BOWL);
       
       server.addRecipe(saplings1);
       
       ItemStack saplings12Stack = new ItemStack(Material.MUSHROOM_SOUP);
       ItemMeta saplings12Meta = saplings12Stack.getItemMeta();
       saplings12Meta.setDisplayName("Sap Stew");
       saplings12Stack.setItemMeta(saplings12Meta);
       ShapelessRecipe saplings12 = new ShapelessRecipe(saplings12Stack);
       saplings12.addIngredient(1, Material.SAPLING);
       saplings12.addIngredient(1, Material.BOWL);
       
       server.addRecipe(saplings12);
       
       ItemStack milkStack = new ItemStack(Material.MUSHROOM_SOUP);
       ItemMeta milkMeta = milkStack.getItemMeta();
       milkMeta.setDisplayName("Chocolate Milk");
       milkStack.setItemMeta(milkMeta);
       ShapelessRecipe milk = new ShapelessRecipe(milkStack);
       milk.addIngredient(2, Material.INK_SACK, 3);
       milk.addIngredient(1, Material.BOWL);
        
       server.addRecipe(milk);
     
       
       
    
       }


@EventHandler
public void OnPlayerSoup(PlayerInteractEvent event){
	Player player = event.getPlayer();
	if(player.getHealth() == 20){
	}else{
		int soup = +7;
		if((event.getAction() == Action.RIGHT_CLICK_AIR || event.getAction() ==Action.RIGHT_CLICK_BLOCK) && player.getItemInHand().getType() == Material.MUSHROOM_SOUP){
			player.setHealth(player.getHealth() + soup > player.getMaxHealth() ? player.getMaxHealth() : player.getHealth() + soup);
			event.getPlayer().getItemInHand().setType(Material.BOWL);
		}
		
		
	}
}
}
